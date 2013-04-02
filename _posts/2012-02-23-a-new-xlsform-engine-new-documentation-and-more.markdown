---
comments: true
date: 2012-02-23 22:28:03
layout: post
slug: a-new-xlsform-engine-new-documentation-and-more
title: A new xlsform engine, new documentation, and more!
wordpress_id: 92
categories:
- Release Notes
---

We have been developing on formhub continuously over the past few months, and a couple of weeks ago upgraded the xlsform engine that formhub uses. Along with the new engine, we have also updated formhub documentation and have established a formhub account called [formhub University](https://formhub.org/formhub_u) where you can learn how to make xlsforms to do the kind of data collection you need!


### XLSform Upgrade


formhub's xlsform engine has been upgraded. Exciting new features include:

  * **Upgraded Syntax**
We have made the syntax for authoring xlsforms simpler. Instead of bind:constraint, you will be writing constraint, and instead of select one from options, you can simply write select_one options. For a preview of the new simplified language, look at our newly updated  [syntax page](http://formhub.org/syntax) or view the  [XLSform standard document](https://docs.google.com/spreadsheet/ccc?key=0AgpC5gsTSm_4dDRVOEprRkVuSFZUWTlvclJ6UFRvdFE).
  * **New Features**
Along with simplification, we have added some language features that were previously missing, such as the ability to do calculations with xlsforms. See the "[Tip Calculator](https://formhub.org/formhub_u/forms/tip_calculator)" on [formhub_u](http://formhub.org/formhub_u/), for example.
  * **Widgets**
All ODK 1.1.7 widgets can now be created using the xlsform language. See the "ODK 1.1.7 Widgets" form on [formhub_u](http://formhub.org/formhub_u/) for an example of widgets, and make sure to follow the instructions listed within the description.

The library (which is currently named pyxform and pending rename to xlsform) is at [https://github.com/modilabs/pyxform](https://github.com/modilabs/pyxform) if you want to browse the source, fork, etc.


### More Documentation


As referenced above, we have updated the formhub [syntax page](http://formhub.org/syntax).

We have also added a [formhub_u account on formhub](http://formhub.org/formhub_u/), where there are surveys that teach you how to write many different kinds of forms:



	
  * [A survey template](http://formhub.org/formhub_u/forms/xlsform_blank) makes it easier to write new forms.
  * [An updated tutorial](http://formhub.org/formhub_u/forms/tutorial) should get you started quickly.
  * [Tip Calculator](http://formhub.org/formhub_u/forms/tip_calculator) shows you how to do calculations and outputs in forms.
  * [Expense Report](http://formhub.org/mberg/forms/expense_report) is an improved version of the expense report form that Matt blogged about on this site.
  * [Child Nutrition Screening Day](http://formhub.org/formhub_u/forms/nutrition_screening) was developed at a training in WHO, and shows a fairly complex real-life example.
  * And finally, the [ODK 1.1.7 Widgets](http://formhub.org/formhub_u/forms/widgets) showcases how to make all the new widgets in ODK 1.1.7, and produces the screens from the [ODK widget examples](http://opendatakit.org/help/form-design/examples/).

### And the features... they keep coming!

We have also been constantly adding new features. We will cover a few of these in future blog posts, but a quick list for anyone who has been waiting are below:






	
  * Media storage in S3 and photo viewing through a galleria plug-in

	
  * ODK Collect authentication support

	
  * Licensing options for forms and shared data

	
  * Support for webforms (preview your survey or do collection on the web)

	
  * Deployment scripts to make the deployment of your own formhub server easier.



