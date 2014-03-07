---
comments: true
date: 2014-03-07 19:38:35
layout: post
slug: View-Formhub-geodata-on-your-phone 
title: View Formhub geodata on your phone
published: true
---

A while ago, on the formhub mailing list, a user asked how formhub data could be view on the phone. He was doing Registration of households, and he was wondering how to load up the data for these households so that surveyors could see which houses to visit when they were going back.

Avid formhub user Erwin Olario thought that viewing .gpx files through an application like [OsmAnd](http://osmand.net) would be a great solution, and has been generous enough to write up his process for the formhub blog:

---

[Formhub](http://formhub.org) lets export your data as a KML file. If you are looking for an option to display this data in your phone, one way to go about it using Open Source tools is to use your Android device for offline navigation. I particularly like [OsmAnd](http://osmand.net) for this purpose but it doesn't read KML files, so the data needs to be converted prior to transferring the data to your device.

### Exporting to KML

If your form collects geographic coordinates, you will find that there's a KML download option available for you on Formhub. This link is visible on the front page of your user account, under "Download" in the "Published Surveys" table.
 
![](http://blog.formhub.org/images/posts/2014/03/kml_export_table.png)

Click the "kml" option to go to the Export KML page. It may take several seconds to generate the file, longer if you have lots of records.  When the export is complete, you will find a link you can click for downloading the generated KML file which you can now save to your computer. 

![](http://blog.formhub.org/images/posts/2014/03/kml_export_page.png)

### Converting to GPX

We need to convert this KML file to GPX format. [GPSBabel](http://gpsbabel.org) converts files to or from many default GPS formats, including those devices made by Garmin or Magellan.  

If you're using some flavor of Ubuntu like I do, (make sure the Universe repository is enabled) from the command line type and run:

    $ sudo aptitude install -y gpsbabel

If you are not faimilar with the command line, you can install the same program using Ubuntu's Software Center. For other platforms, please visit [GPSBabel's official download page](http://gpsbabel.org/download.html) for binaries you can install.  To convert a KML file, run from the command line:

    $ gpsbabel -w -i kml -f "in.kml" -x nuketypes,tracks,routes -o gpx -F "out.gpx"

The command issue above tells GPSBabel to ignore tracks and routes and just use the waypoints found in "in.kml" (or whatever file name you used when you downloaded it to your computer) and save them in GPX format as "out.gpx" (or choose your own.)

Now, if you don't want to install anything in your computer, there's a GPSBabel web interface hosted by a third-party: [GPS Visualizer: GPSBabel](http://www.gpsvisualizer.com/gpsbabel/). Just make sure you set the option to convert to Waypoints, and that your input file format is Google Earth (Keyhole) Markup Language and the output format is GPX XML, upload your file and hit the Convert the file button.

![](http://blog.formhub.org/images/posts/2014/03/gps_babel_webview.png)

### View it in your device

Your file is almost ready for use in your Android device. Make sure to have a GPX reader and import the data. If you don't have any, I recommend OsmAnd - and as Prabhas pointed out, not only can you view your POIs, you also view the map offline, using the excellent and community provided data from [OpenStreetMap](http://osm.org).

![](http://blog.formhub.org/images/posts/2014/03/OsmAnd.png)

If you use OsmAnd, make sure that you copy your GPX file to the following location because it doesn't have a built-in import capability, so it expects GPX tracks in the same folder like so:

    $ osmand/tracks/out.gpx

Launch OsmAnd, and configure the view to display Favorites and GPX tracks. Your waypoints are displayed as stars, the same icons used for favorites. For details on how to setup your OsmAnd app, please visit the very good collection of How-Tos in the [OsmAnd wiki](https://code.google.com/p/osmand/wiki/HowToArticles).

For a few screenshots of how I use this in OsmAnd, I have an album [here](https://plus.google.com/photos/+WinOlario/albums/5984150774113636385?authkey=CKmW8Ka41JuDfA).
