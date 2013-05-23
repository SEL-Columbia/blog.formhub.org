---
comments: true
date: 2011-10-20 14:21:49
layout: post
slug: google-docs-bootstrap-and-django
title: Google Docs, Bootstrap, and Django
wordpress_id: 12
categories:
- Tech
---
*Andrew Marder*

Writing good documentation quickly is a hard. Sphinx is great at auto-generating documentation from code, but it's slow to write additional documentation in reStructuredText and not everyone is comfortable writing with a markup language. To work around this barrier to entry we decided to write some of our documentation using Google Docs, then using some features of Django we were able to incorporate the living document directly into our site. Here is the before and after comparison:

[![](https://github.com/modilabs/formhub/wiki/images/input.png)](https://docs.google.com/document/pub?id=1Dze4IZGr0IoIFuFAI_ohKR5mYUt4IAn5Y-uCJmnv1FQ#h.92ndqcrwx98v)![](https://github.com/modilabs/formhub/wiki/images/output.png)

Or see it in action here: [http://formhub.org/syntax/](http://formhub.org/syntax/)

<!--more-->

Here are some tidbits I found interesting when making this tool:

  * Google Docs uses peculiar section IDs. Instead of using 'h.92ndqcrwx98v' I decided 'introduction' would make a prettier link.
  * Google Docs fakes unordered lists and nested lists. For some reason, the HTML export of the document doesn't have the prettiest HTML. I was particularly frustrated that when I nest one list inside of another the HTML version ends up have three lists one after another with special formatting to make it look like they are nested.
  * The tables worked out quite well. Some information is lost, but the column widths are fairly well preserved and this will save a ton of time formatting because formatting a Google Doc table is way easier than formatting an HTML table.
  * It would be nice to have the table of contents float on the right side of the page. Unfortunately, this feature doesn't come out of the box with Twitter Bootstrap, so if anyone knows an easy way to make this happen, please let us know.

If you're curious to see how this works, check out the code [here](https://github.com/modilabs/formhub/blob/master/main/views/google_doc.py), I've commented it heavily to explain how everything works.

Andrew Marder

