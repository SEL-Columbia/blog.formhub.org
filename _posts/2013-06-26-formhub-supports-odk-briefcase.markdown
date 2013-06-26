# Formhub supports ODK Briefcase

ODK Briefcase is used to gather and export data from an ODK Aggregate server e.g [formhub.org](https://formhub.org) or from ODK Collect when you are offline.
posts/2011-12-09-staying-even-how-to-use-formhub-and-odk-collect-to-track-your-travel-expenses.markdown
1.  Export forms with submissions from formhub (ODK Aggregate) - PULL 

*   Make bulk submission to formhub (ODK Aggregate) - PUSH

*  CSV exports of submission data

*  Pull forms and submissions collected by ODK Collect from a mobile phone

*  Supports encrypted forms: it can make encrypted submissions to formhub as well
    as decrypt encrypted submissions from formhub when exporting the data to csv.
     
     
If you have encrypted forms and making submissions to formhub, you’ll realise 
that you do not have the ability to browse the submitted data on the site.
Formhub stores the submissions in encrypted form, using your private key and 
ODK Briefcase you can be able to pull your data from formhub and export it 
to a csv  file.

**How to setup ODK Briefcase to work with formhub**

1. Install Java 6 or higher on your computer.

*  Download ODK briefcase from [http://code.google.com/p/opendatakit/](http://code.google.com/p/opendatakit/)

*  Specify the location of the ODK storage area on your computer this will 
   create the ODK Briefcase Storage folder which will hold all the blank
   forms and finalized forms(submissions).
   
*  Open ODK Briefcase.

*  On the tab "Pull," click on the bar to the right of "Pull data from:" 
   (top left) and choose "Aggregate 1.0".
   
*   Click on "Connect" to pull data from aggregate

![](/http://www.flickr.com/photos/97973954@N06/9140785103/sizes/z/in/photostream/)

7.  Specify the formhub url, enter the username and password to your formhub account.
    Click "Connect” to pull forms from formhub.
  
![](/http://www.flickr.com/photos/97973954@N06/9140785689/)

8.  In the main screen, find the form you want to download and tick off on the 
    check box to the left of it.
    
![](/http://www.flickr.com/photos/97973954@N06/9143039988/)

9.   Hit "Pull" button at bottom right of page.

![](/http://www.flickr.com/photos/97973954@N06/9140794389/)

10.  Wait until you see the "SUCCESS!" message on the "Pull status”.

![](/http://www.flickr.com/photos/97973954@N06/9143022580/)
— 
**Using ODK Briefcase to export data from formhub** 
1. Go to “Export” tab. Pull down the bar to the right of "Form:" (top left) 
   and choose the relevant form. 

![](/http://www.flickr.com/photos/97973954@N06/9143049274/)   
   
2. Click on the "Choose" button to the right of the 3rd row (Export Directory) 
   and select from the directory location.
   
3. Click "Export" button on the bottom-most right of the application. 
   This will  load  quickly and will give you the same "SUCCESS!" message





    
    


    
















