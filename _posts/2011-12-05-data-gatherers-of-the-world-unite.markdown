---
comments: true
date: 2011-12-05 13:55:23
layout: post
slug: data-gatherers-of-the-world-unite
title: Data Gatherers of the World Unite!
wordpress_id: 30
---

We are really excited to announce the beta release of [formhub](http://formhub.org), a service for making data collection **simpler** and **more collaborative**. Great projects like the Open Data Kit (ODK) project have provided us with very simple tools to collect data, but the process of authoring surveys and going from survey specification to data has always been cumbersome, and accessible only to highly technical users. formhub aims to make the whole data collection process simpler and more collaborative.

formhub makes data collection **simpler** by making survey authoring simpler, and by providing a hosted site in which going from authored survey to data is quick and painless. formhub has already been used to collect data for more than 12,000 surveys, and the process that inspired formhub was used to collect data on more than 30,000 facilities, so we know it works at scale.

formhub also makes data collection **more collaborative** by working with a human-readable format for authoring xform-based surveys. This new format, XLSform, is based on an underlying excel file, which anyone with access to Microsoft Office, LibreOffice, or Google Docs can edit. Being both human-accessible and machine-readable also makes XLSforms an ideal format with which to share survey specifications once surveys have been fully vetted and authored.

## The XLSForm Standard

Much of our work at the Modi Research Group involves building large complex forms for surveys that often involve hundreds of questions, need to be available in multiple languages, and need to be vetted by multiple people in multiple teams. To help with this process, one of our engineers, Andrew Marder, came up with a way to author the forms in Excel (we then convert them into XForms using a tool called XLS2XForm). We found that web-based form builders were great for building simple forms but were cumbersome as the size and complexity of forms grew. Machine-interpretable surveys in excel files, on the other hand, enabled us to use great tools like Google Docs, Microsoft Excel, and dropbox to manage our surveys. These excel files allowed us to share forms and get feedback from multiple non-technical teams. The excel files are easy to interpret, easy to edit, and thanks to Google Docs extremely easy to collaborate on.

**Human Readable**

We’re excited by the XLSForms because we feel they are both machine and human readable, and we hope they can be viable standard for sharing data collection tools.  The xform, which was designed to do this, allows for great interoperability between machine systems but is almost impossible for normal people to read.  As a result, forms are shared in PDF or Microsoft Word-based formats, which can’t easily be converted into a digital data collection process. With XLSForms, you get surveys that are readable with a human eye, as well as by machines. This makes them an ideal format for sharing: as people collaborate over survey design, or once the survey is designed and the need to share with additional partners or the public at large (in a re-usable format) arises.

_See what we mean about readability? (Pictures are parts of xform and xlsform specifying the same survey)._

![](https://lh6.googleusercontent.com/Rf7ZectmEC51EVsNfMyhIPyuhytE07PnITBdLxvwb1wEkFSUSoYgNP3OO6439Ho7-qS1WdmFEjY2l-DwmzAW_YUn34yg1dt1rowCnoTQXmV7kuxVH5I)

![](https://lh5.googleusercontent.com/ynVVTqMxoV28vLMR0X1KNcQTSSYNLEQOyy3-U6OGMzkMIF-5oSER9IKjycLO8yv21f65FEkZsZ_e6n07-C6zpYZdz5yT-0eeSHsFYtjUF3s1aSazHJo)

<!--more-->


## Shareable

We built formhub around the idea of sharing forms. Sharing forms during survey design, the first point of need for sharing can be done using email and Google Docs. But once a survey is ready and published on formhub, we want to allow survey designers to share their data collection tools with the public or partners they collaborate with. One of the most exciting features on formhub will be this feature—to be able to share an XLSform (an excel file) which has been published as a survey. We don’t have this sharing feature ready yet, but its coming, and we couldn’t be more excited about building it.

## Simple End-to-End Data Collection

In addition to allowing everyone to use an easy to share and collaborate medium for defining surveys, formhub allows painless deployment of data collection efforts. The process for deploying a survey through formhub is very simple, and no technical setup knowledge is required.

The survey deployer simply:

  * signs up for an account
  * writes a survey in the XLSform format
  * submits the XLSform to formhub

On the data collection side, the data collectors can leverage ODK’s workflow, and simply need to:
	
  * configure ODK’s server preferences to point to the appropriate formhub username
  * download the appropriate form
  * conduct the survey
  * and submit the data.

The data is then immediately available for viewing on a google map or for download from formhub as CSV or Excel files. In demonstrations and trainings, new users have been able to sign up for an account, write simple surveys, deploy them, and get incoming data in a span of minutes.

If you have a half an hour to spend, we suggest you to try it yourself!

## formhub in Five Words

We hope formhub becomes the _hub_ of your _mobile data collection needs_.

**Simple.**
All you need to get started is an account on formhub, and an ability to author .xls files. There is absolutely no technical setup required.

**Collaborative.**
The format that formhub uses, XLSForm, were designed with collaboration in mind. It allows multiple authors to work on the same survey, but even more, once the survey is designed, for survey authors to share their surveys with the world.

By enabling the sharing of forms, we hope to foster a collaborative community of data collectors. In many ways, sharing data collection instruments equates to sharing best practices. The standardization of particular forms promotes data standards.

**Secure.**
We want to provide a safe and secure (https coming soon) place for your data.  We’re working to make sure all data will be backed up in the cloud. At anytime you can easily export your data in excel or CSV formats.

**Free (as in beer).**
Our goal is to provide a free (as in beer) service (no question or submission limits) to allow you to publish a form to a phone and begin collecting data. We aim to keep this service free to not limit access to this service. If eventually our hosting costs get unsustainable we’ll work with the community of users to figure out a way forward.

**Free (as in speech).**
The underlying code for formhub is[ freely available](http://github.com/modilabs/formhub) under an opensource license.  We wanted to make it easy to host your own formhub instance if you like and if you’re a developer we’d welcome code contributions.  We built formhub in Python and Django since that’s what we’re comfortable using.  If you like Java there are other excellent back-ends available like[ ODK Aggregate](http://opendatakit.org/use/aggregate/) that we encourage you to checkout.

## And Finally, Some Caveats


Please mind the bumps. This is a work in progress but we’ll endeavor to keep your data safe. We are still working on some core features like sharing, but wanted to get the tool out as its already quite useful!

You can help by providing feedback, ideas for features, reports of bugs and of course compliments!   Knowing we’re providing a helpful tool is what keeps us going.




