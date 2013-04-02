---
comments: true
date: 2012-08-30 23:40:27
layout: post
slug: nyc-and-nairobi-devs-connect
title: NYC and Nairobi devs connect
wordpress_id: 198
---

The majority of recent formhub programming has been performed by the development team in Nairobi.  For two weeks in July, part of the New York City formhub development team got a chance to work with the team in Nairobi.  We learned about all the recent additions to formhub from a technical perspective, set some priorities for the future, and --- of course --- did some coding.

[![](/images/posts/2012/08/nairobi_office_projector.jpg)](/images/posts/2012/08/nairobi_office_projector.jpg)

We worked out of a spare classroom, and made ample use of a projector to review code and make architecture decisions --- some functions just make more sense when they are life size.  In the photo above, Ukang'a Dickson stands next to the fabfile, figuring out how to [deploy a specific branch](https://github.com/modilabs/formhub/blob/master/fabfile.py#L60) with a one liner.

Of course we didn't spend our whole trip coding in front of a projector.  In the photo below we are on top of the Kenyatta Conference Center in downtown Nairobi.  It is the second tallest building in Nairobi, and you can see the Times Tower, the tallest building in Nairobi, right behind us.

[![](/images/posts/2012/08/IMG_20120714_153626.jpg)](/images/posts/2012/08/IMG_20120714_153626.jpg)

Also during our coding sessions Larry Weya led us through the new export code.  We refactored the existing export code and it now provides a more unified interface for different export formats with all the data coming from a parsed version of the raw XML submissions.  For the end user, this allows formhub to support deletion of individual records, selective processing on export, and other features.

[![](/images/posts/2012/08/Modi_Research_Group_-_CGC_Presentation_-_July_2012.gif)](/images/posts/2012/08/Modi_Research_Group_-_CGC_Presentation_-_July_2012.gif)

We also gave a presentation to the members of the Columbia Global Center in Nairobi, and some guests.  Our presentation included the above and now out of date slide.  204,654 submissions is so last month, as of August 30th 2012 formhub is now at 272,300 submission and counting...
