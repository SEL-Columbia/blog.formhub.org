---
comments: true
date: 2011-12-09 23:56:37
layout: post
slug: staying-even-how-to-use-formhub-and-odk-collect-to-track-your-travel-expenses
title: Staying Even - How to use formhub and ODK Collect to track your travel expenses
wordpress_id: 44
---

I travel a LOT and like most people who do struggle to keep track of my reimbursable travel expenses. My memory blurs between trips and I forget about all the cab rides where I don't bother to get a receipt.  As a result, whenever, I get around to finally filing an expense report (the bane of my existence) it usually consists of the big ticket items with receipts that didn’t erase themselves.  Long story short, the cost of me being lazy and unorganized adds up.
[![](/images/posts/2011/12/Screen-Shot-2011-12-09-at-6.49.17-PM.png)](/images/posts/2011/12/Screen-Shot-2011-12-09-at-6.49.17-PM.png)

Recently, I thought I’d try keeping track of my expenses on my android phone (cause it’s always on me) using [ODK Collect](http://opendatakit.org/) and [formhub](http://www.formhub.org). I know there are a ton of travel expense apps out there but the idea of being able to tailor the content to my particular needs: foreign currency, rickshaw rides... appealed to me. So far it’s been working pretty well for me and here’s what I did.

First, I designed the following expense report form in excel ([expense_report.xls](https://formhub.org/mberg/forms/expense_report/form.xls)).  It’s very straightforward consisting of things like the expense type, description, amount and currency with the option of taking a photo for the receipt (or activity) and GPS of the location (if I really want to go back and find that kebab stand). I then upload it to my formhub account, which allows me to access it ODK Collect on my phone when I need it.  For detailed instructions on how to do this see [here](http://www.formhub.org/tutorial).   When I’m done with a trip, I get a clean export of my expenses in excel in the format I defined and if I log the location, I can even see where I traveled on a map which is kind of fun.

**Customizing for my trips**

Since excel is so easy to modify, I usually customize my [expense report template](https://docs.google.com/spreadsheet/pub?hl=en_US&hl=en_US&key=0AgpC5gsTSm_4dGxDOXpSdGwtUlVvLVY1TWZ1VzVmS0E&output=xls) to tailor it to my upcoming trip.  For example, I add or remove things like currencies I need on a trip. If my trip is domestic, I usually remove the currency question all together as I know I’ll only be spending dollars.

Another nifty trick, is to rename the name of the excel form before uploading to reflect the name of the trip.  For example, ER_ghana_nov11.xls. This allows me to easily keep my expenses segregated between trips and a nice historical record of my trips in my formhub account.

[
](/images/posts/2011/12/Screen-Shot-2011-12-09-at-6.44.46-PM.png)[![](/images/posts/2011/12/Screen-Shot-2011-12-09-at-6.44.46-PM.png)](/images/posts/2011/12/Screen-Shot-2011-12-09-at-6.44.46-PM.png)

**DIY Data Apps**

What I really like about this setup is that I can quickly develop a pretty robust data collection app suited to my exact needs. On my phone,  I only need to install a single app providing me a consistent interface that I like and all my data is stored in a data format I define safely online and not on my phone which can be lost or stolen.

Plus, if someone else comes up with a cool app idea, I can just grab their XLSForm and use/adapt it myself. All this has got me thinking about that street meat map, I want to make!
