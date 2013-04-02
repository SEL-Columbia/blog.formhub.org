---
comments: true
date: 2012-08-17 20:49:41
layout: post
slug: new-in-formhub
title: New in formhub...
wordpress_id: 192
---

At formhub, we don't have versioned releases. Instead, we follow the "[continuous integration/deployment](http://en.wikipedia.org/wiki/Continuous_integration)" model. While we deploy updates [nearly as frequently as some](http://timothyfitz.wordpress.com/2009/02/10/continuous-deployment-at-imvu-doing-the-impossible-fifty-times-a-day/), we do push updates quite frequently; often more than once a day. This makes the standard announcement of features per release a little tougher, so I've tried to start a "new in formhub" post per week over at [formhub-users](https://groups.google.com/group/formhub-users). Here are the last two:

_**Posted on Friday, August 17:**_

  * formhub now serves up the media you upload to it properly to ODK collect. For those of your working with media in your forms, the process should become much more seamless now. Check out the [Birds form on formhub_u](http://formhub.org/formhub_u/forms/Birds) to see how this works. (adapted from the odk forms [repo](https://code.google.com/p/opendatakit/source/browse/?repo=forms)) 
  * A new header and other stylistic changes. We have begun a process of the UI revamp on formhub, and a new header, typography, and other stylistic changes were pushed up this week. Hope you like them!
  * Leaflet upgrade. We upgraded the mapping library we use, leaflet.js to [0.4](http://leaflet.cloudmade.com/2012/07/30/leaflet-0-4-released.html). You may notice a few little changes on the map, like a smoother zoom.
  * IE 0.9 fix. During the addition of google satellites, we accidentally broke the map view for IE 0.9 users. That has been fixed.
  * Data posts to bamboo as they come into formhub working. This will sound cryptic to most. But once our web-data-analysis engine bamboo is released, this feature (continuous updates) will make many of you happier :)

_**Posted on Friday, August 10:**_

  * formhub can now update an external webservice with data as data is submitted to formhub (see [the blogpost](http://blog.formhub.org/2012/08/06/posting-to-external-site/) for details)
  * Google Satellite Maps are now available as a background on the map view
  * formhub's xlsform engine now has a "hidden" field (which only takes a "name") which outputs a bind element, and  a space in the instance, but nothing in the body -- this was added for those using formhub as an xform-generation engine to produce xforms for commcare, which makes use of these 'hidden' fields to load case data
  * i18n support: formhub now has the infrastructure to support site-wide translations. Those with their [browser locale settings](http://www.w3.org/International/questions/qa-lang-priorities.en.php) set to French should already see quite a bit of the site translated.


