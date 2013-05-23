---
comments: true
date: 2013-01-11 07:58:41
layout: post
slug: account-activity-log
title: Account activity log
wordpress_id: 255
---

Many data collection projects have strict research protocols on how data can be accessed or modified.  To help with with this, we're excited to announce that we've added activity/audit logs to formhub.  This allows you to view what actions have been performed on your formhub account, by which user(s) and at what times. To access this log, click on the little arrow next to your username and select "Account Activity" from the list.

**The Account Activity page**

The activity list has these 4 columns:

  1. Performed On - The date and time that the action was performed
  2. Action - The name of the action performed
  3. Performed By - The username of the user who performed the action
  4. Description - A short description of what was exactly done and what it affected

[![](/images/posts/2013/01/Screen-Shot-2013-01-15-at-10.35.58-PM.png)](/images/posts/2013/01/Screen-Shot-2013-01-15-at-10.35.58-PM.png)


Initially, the list will display the most recent activity first, this sort order can be changed by clicking on the "Performed On" column header (or any of the other columns headers to sort by them).

<!--more-->

**Filtering the activity list**

You can perform a filter on the activity list to for example look at any form delete actions. There are two ways to perform filters.

  1. Using the general search box labelled "Search data...". This search looks through each of the fields for whatever you type in. It is fine for a general search but you cannot for example search for actions within a specific time period.
  2. Using the filter box on the right to search through specific fields. This allows you to specify which field to search through and allows you specify strict criteria. E.g. to search for activity between two dates, click on "Add Filter", leave the field as "Performed On" and change type to **Range** and click **Add** to add the filter. The **Range** filter type allows you to specify the start and end values of the range via the **From** and **To **fields. Clicking on either will display a date picker that would allow you to specify the date. As of this writing, you will have to specify the time by typing it in manually. Click on "Update" to apply the filter.

The filter can also be used to search for specific actions from a list of pre-defined actions. To do this, start by clicking on "Add Filter." Change the field to "Actions" and the filter type to "Options" and add the filter. This will display a dropdown with the list of available action types as follows:

* public-profile-accessed - When the account's profile is accessed by anyone other then the owner
* profile-settings-updated - When the account's settings are updated
* bulk-submissions-made - When a bulk submission is made to the account
* form-accessed - When a form on the account is accessed. The description will include the name of the form
* form-published - When a form is published
* form-updated - When a form's seetings are updated, the description will include which settings were updated and what the values were changed to
* form-xls-downloaded - When the source XLS file is downloaded
* form-xls-updated - When an existing form's XLS is updated
* form-deleted - When a form is deleted
* form-cloned - When a form is cloned
* form-permissions-updated - When the form's sharing permissions are updated
* form-enter-data-requested - When the web form entry is initiated
* form-map-viewed - When the form page is opened
* form-data-viewed - When the form's data is viewed through the various web views
* export-created - When an export is created
* export-downloaded - When an export is downloaded
* export-deleted - When an export is deleted
* submission-created - When a submission is made
* submission-deleted - When a submission is deleted
* submission-edit-requested - When a submission edit is requested. When the edit is complete, it will be logged as a submission-created
* bamboo-link-created - A link to the bamboo service is created
* bamboo-link-deleted - A link to the bamboo service is deleted





