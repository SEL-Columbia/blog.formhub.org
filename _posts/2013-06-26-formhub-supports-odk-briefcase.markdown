# Formhub supports ODK Briefcase

ODK Briefcase is used to gather and export data from an ODK Aggregate server e.g [formhub.org](https://formhub.org) or from ODK Collect when you are offline

ODK Briefcase can: 

1. Export forms with submissions from formhub (ODK Aggregate) - PULL 
*  Make bulk submission to formhub (ODK Aggregate) - PUSH
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

![](http://farm4.staticflickr.com/3754/9140785103_e2b7522189_o.png)
7.  Specify the formhub url, enter the username and password to your formhub account.
    Click "Connect” to pull forms from formhub.
    
![](http://farm3.staticflickr.com/2805/9140785689_77aefd32cf_o.png)
8.  In the main screen, find the form you want to download and tick off on the 
    check box to the left of it.
    
![](http://farm3.staticflickr.com/2832/9143039988_2c27f93e44_o.png)
9.  Hit "Pull" button at bottom right of page.

![](http://farm3.staticflickr.com/2885/9140794389_af9fc64363_o.png)
10.  Wait until you see the "SUCCESS!" message on the "Pull status”.

![](http://farm4.staticflickr.com/3753/9143022580_819c802647_o.png)


**Using ODK Briefcase to export data from formhub** 

1.  Go to “Export” tab. Pull down the bar to the right of "Form:" (top left) 
    and choose the relevant form. 
   
![](http://farm8.staticflickr.com/7281/9143049274_dc072d8ccb_o.png)  
2. Click on the "Choose" button to the right of the 3rd row (Export Directory) 
   and select from the directory location. 
   
3. Click "Export" button on the bottom-most right of the application. 
   This will  load  quickly and will give you the same "SUCCESS!" message.
   
   
**Get data off your phones and do bulk submissions with ODK Briefcase**

This can be done when you are offline and you are unable to make your submissions to formhub immediately due to slow or lack of internet connectivity.

To make bulk submissions to your PC:

1. Make sure that ODK Briefcase is downloaded to your PC.
2. Mount your smartphone to your computer using the USB cable.
3. Create a folder to save survey data into. For example in our case the folder was
   named “Surveys”   
*  Open ODK Briefcase
*  On the tab "Pull," click on the bar to the right of "Pull data from:" 
   (top left)  and choose "Mounted Android SD Card"
   
 ![](http://farm6.staticflickr.com/5516/9143072064_34582d54a0_o.png)
 
6. In the next row, choose the relevant SD Card

![](http://farm4.staticflickr.com/3811/9140828551_bf9b74f1bd_o.png)

7. In the main screen, find your survey and tick off the check box to the left of it

![](/http://farm8.staticflickr.com/7412/9143058348_909077c651_o.png)

8. Hit "Pull" button at bottom right of page

*  Wait until you see the "SUCCESS!" message on the application as shown on the 
   figure below
   
   
![](/http://farm4.staticflickr.com/3769/9143060470_d8dd0efed9_o.png)

10. Now go to the "Export" tab

*  Pull down the bar to the right of "Form:" (top left) and choose the 
   relevant  survey

*  Hit the "Choose" button to the right of the 3rd row (Export Directory) and 
   choose  the fold
   
![](/http://farm4.staticflickr.com/3831/9140835869_9da6503985_o.png)

13. Click "Export" button on the bottom-most right of the application. This 
    should load very quickly and will give you the same "SUCCESS!" message
    Repeat the process for the forms in the SD card that you would like to 
    export to the folder created on your computer.
    
*  Now the data is all in the folder.

**Note:**
As new data is being submitted to formhub, ODK Briefcase will intelligently pick only the new and updated submissions

ODK Briefcase allows you to have a local copy - backup - of your data on formhub.


    












   
   





    
    


    
















