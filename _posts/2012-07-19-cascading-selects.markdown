---
comments: true
date: 2012-07-19 04:50:29
layout: post
slug: cascading-selects
title: Cascading Selects
wordpress_id: 150
---

Within the [Modi Research Group](http://modi.mech.columbia.edu) (informally known as modilabs), we are constantly creating new ways to improve the xlsform-based data collection process. Sometimes we are so busy thinking of new things and implementing them that we don't even announce some of the features we have introduced to make data collection simpler and easier. This time around, I want to talk about cascading-selects, a feature that we introduced into xlsform / formhub a couple of months ago, and which intrepid user Nikolai has dug up and [started spreading](https://groups.google.com/d/topic/opendatakit/JHAbgh1kKOs/discussion) around (thanks Nik for forcing us to write this blog post :).

**The problem**

Say you want to do data collection, and present the user with a series of selection questions, where the answer depends on a previous selection. The classic example is asking someone to enter a district in a country. But you don't want the user to deal with 777 options at once (example from Nigeria), so you present enumerators with a question asking them about the zone they are in (6 in the country), the state they are in depending no the zone (less than 10 per zone), and then, finally, the LGA, depending on the state they are in.

Turns out that this is possible with xlsforms without cascading select, but it requires you to write out one question per state in this case (36 different questions), with a fairly complex criteria in the relevant column. And even then, the end information you care about is what zone, state, and LGA the enumerator has filled out information about. Calculating this information requires writing a gigantic if statement, with the same number of branches as there are states in the country! This is quite an unimaginable process, so people have to resort to something like using a different tool for the job, like Kobo Collect. We wanted to make a tool so people could use formhub painlessly and still collect cascading-select information.

**The feature**

****Since xlsforms are computer processed, we introduced a feature called cascading-select, where the user is able to simply list the cascading relationships. In a sheet called `cascades` the xlsform needs a table like so:









name


zone


state


lga






label


Choose your zone:


Choose your state:


Choose your lga:






choice_label


Zone 1


State 1


LGA 1






choice_label


Zone 1


State 1


LGA 2






choice_label


Zone 1


State 2


LGA 3






choice_label


Zone 1


State 2


LGA 4






choice_label


Zone 2


State 3


LGA 5






choice_label


Zone 2


State 3


LGA 6






choice_label


Zone 2


State 4


LGA 1






choice_label


Zone 2


State 4


LGA 2




And in the survey sheet, a simple question like:








type


name






cascading_select lga


mylga




will present the user with three questions (which one shows up totally depends on previous input):

[
](/images/posts/2012/07/2012-07-19_08-39-20.png)

[![](/images/posts/2012/07/2012-07-19_08-39-20-168x300.png)](/images/posts/2012/07/2012-07-19_08-39-20.png) [![](/images/posts/2012/07/2012-07-19_09-58-52-168x300.png)](/images/posts/2012/07/2012-07-19_09-58-52.png) [![](/images/posts/2012/07/2012-07-19_08-39-43-168x300.png)](/images/posts/2012/07/2012-07-19_08-39-43.png)

[
](/images/posts/2012/07/2012-07-19_08-39-43.png)

But underneath the hood, xlsforms will generate 7 different select-one questions (1 for the zone, 2 for the states (per zone), and 4 for the LGAs (per state)), and write the appropriate skip logic to ask them given the right prior selections. [ref] Try it our yourself! Go to [the forms page on formhub](http://formhub.org/forms), search for "cascad" , and clone any of the forms that show up there. The one I have worked above is available [here](http://formhub.org/pld/forms/cascading_select_test) or [here](http://formhub.org/prabhasp/forms/cascading_select_test_cloned). [/ref]

And even more, there will be calculations added to the form, so that if you want to know the zone, the state, or the LGA of your submission, you can just look for variables called mylga, mylga_state, and mylga_zone in this case. The "mylga" bit was obtained from the name assigned to the cascading select, and the "state" and the "zone" respectively from the "name" row in the "cascades" sheet.

[![](/images/posts/2012/07/Screen-Shot-2012-07-19-at-10.12.27-AM.png)](/images/posts/2012/07/Screen-Shot-2012-07-19-at-10.12.27-AM.png)

The above is a simple test case, and may not seem impressive. But when you're dealing with 777 LGAs, like we were in Nigeria, the feature can be a life-saver. The nice bonus is that admin boundary data is stored in a format that corresponds very closely to the cascades sheet.

**The limitations / the future of cascading-selects**

Those intimately familiar with xlsforms will wonder: so we specified the "label"s for each of the options above, but where are the "name"s for each of the options? xlsforms derives the names directly from the label, but knocking out capital letters, and replacing all non-alphanumeric with an underscore. This makes the form-authoring convenient, but introduces a major limitation (and perhaps the main reason we haven't been all-drums-blaring about cascading-selects). This automatic name derivation, which departs from the xlsform norm, means that not only are we missing the ability to create custom slugs (such as digit codes for districts), but the multiple language support in the rest of xlsform falls through :( [ref] We do have ideas about how to take cascading selects to a form which supports name/label pairings and multiple languages, so if there is a team out there with developer resources available and wanting to expand this feature, please get in touch with us at support@formhub.org. As always, you can check out (in this case, a possibly hairy) implementation at http://github.com/modilabs/pyxform [/ref].

The second limitation is that we use javarosa without itemselects, which means that the xform that ODK collect evaluates contains many many questions with a long menu of options, and a really complex calculation. ODK actually crashed for us at the level of complexity of 777 LGAs in 36 states (although half that number was okay). A better approach might be to use new javarosa itemselects; we haven't explored this path yet, but likely will soon, as ODK Collect 1.2 will soon come out with item-select support..

The third limitation is a bug that is easy to get around, but might catch you by surprise. Because the code generates a name based on the label, if you have two states with the same label (but in two different zones), cascading selects won't work properly. It will handle LGAs (i.e., leaf-level options) with the same label in two states, but two states with the same name will cause problems. The solution, if you encounter this, is to change the spelling of one state (adding spaces at the end should suffice, but please do check that it does).

[
](/images/posts/2012/07/Screen-Shot-2012-07-19-at-10.12.27-AM.png)
