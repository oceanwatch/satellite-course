---
description: >-
  Written by Cara Wilson (CWWC). Adapted by Ron Vogel (CWEC) and Melanie
  Abecassis (OWCP)
---

# ERDDAP tutorial

**Objective:**   
  
Showcase the breadth of datasets available on various ERDDAPs and demonstrate how to graph and download data from ERDDAP.

## Familiarizing yourself with ERDDAP

ERDDAP was developed by Bob Simons from the NOAA SouthWest Fisheries Science Center.

ERDDAP is a platform to distribute data to users. Various institutions have installed ERDDAP to allow their users to visualize and download data. 

ERDDAP offers a consistent way to get data from a variety of different data sources.   
A variety of data types can be distributed on ERDDAP: in situ, satellite, or model data among others. 

ERDDAP lets you download data in your preferred data file format \(netcdf, csv, ESRIcsv, JSON, ODVtext, mat, text and more\).

ERDDAP lets you create images in your preferred image file format \(png, transparent png, pdf, kml\). 

It supports temporal and spatial subsetting. 

It is “RESTful”, meaning the URL completely defines the data you want, in the format you want. This means you can transfer the URL to another application and access the same data from there, for example, in your own webpage, or from your analysis software. You can even email the URL to a colleague and they can access the same data, image or plot that you generated.

 So ERDDAP works for both humans and machines!

## A short list of ERDDAP instances

* [CoastWatch West Coast ERDDAP](https://coastwatch.pfeg.noaa.gov/erddap/index.html) 
* [OceanWatch Central Pacific ERDDAP](https://oceanwatch.pifsc.noaa.gov/erddap/index.html) 
* [APDRC ERDDAP](https://apdrc.soest.hawaii.edu/erddap/index.html) 
* [PACIOOS ERDDAP](https://pae-paha.pacioos.hawaii.edu/erddap/index.html)

## Which ERDDAP should I use?

If you are unsure of which ERDDAP hosts the dataset you are interested in, you can use the following search engine, which compiles data hosted by 49 different ERDDAP instances across the world:  
  
[https://irishmarineinstitute.github.io/search-erddaps/](https://irishmarineinstitute.github.io/search-erddaps/)

## Example \#1. Examine the Kilauea algae bloom

![](../.gitbook/assets/image%20%28105%29.png)

Following the 2018 lower Puna eruption, an algae bloom was observed off the east coast of the Big Island in June 2018 \(visible near the easternmost point of the island if you zoom in\). 

Let’s see what the chlorophyll concentration data looks like for that period.

* Go to the OceanWatch ERDDAP
* Type “MODIS chlorophyll” in the search box.  This will generate a list of choices
* Hover with your mouse on the question mark in the “Summary” column for some of the rows.  This is where you can find a brief description of each dataset 
* Click on the “graph” link to the left of the dataset named “Chlorophyll a Concentration, Aqua MODIS - 8-day, 2002-present. v.2018.0” 

Here is what you should see. 

![](../.gitbook/assets/image%20%28130%29.png)

You'll notice that for this dataset, longitudes go from 0º to 360º instead of -180º to 180º. This allows users to download data for regions across the dateline. Other data sources, not focused on the Pacific, provide the data with longitudes between -180º and 180º. 

Notice also that for this dataset, latitudes go from North to South.   
Some datasets list the latitudes from south to north.

You should always check the range of longitudes and latitudes for each dataset you are working with to make sure you are downloading data for the correct region and to avoid error messages.

* Enter 18 and 23 as the south and north latitude and 200 and 208 as the start and stop longitude. 
* set the date to 06/02/2018
* Adjust the colorbar minimum to 0.005 
* Click on “redraw the graph”

![](../.gitbook/assets/image%20%28118%29.png)

Scroll through the different time steps using the + button next to the date to see the full extent of the bloom. You can also adjust the color scale by setting different values for colorbar minimum and maximum.   
Don't forget to click on "Redraw the Graph" after you change settings.

Under the "redraw the Graph" button, set the file type to ".largePng" and click on the "download" button. Try different file type options \(html, PDF, ...\).

## Sharing the map

After making all these changes, when the map looks the way you want it to, you can easily share it, or save it by simply copying the URL in your browser.

![](../.gitbook/assets/image%20%28177%29.png)

## Griddap versus Tabledap

There are two types of data stored on ERDDAP – gridded data \(i.e. satellite data\) and tabular data \(i.e. station or profile data\). ERDDAP uses two different functions to deal with the different types of data. Griddap works with gridded data and Tabledap works with tabular data. 

Got to the [PACIOOS ERDDAP](https://pae-paha.pacioos.hawaii.edu/erddap/index.html) and click on "View a list of all 163 Datasets".

![](../.gitbook/assets/image%20%2882%29.png)

You can see that there is a "GridDAP" column and a "TableDAP" column, corresponding to different datasets.

## Example \#2. Look at PIFSC CTD data

Go to the [OceanWatch Central Pacific ERDDAP](https://oceanwatch.pifsc.noaa.gov/erddap/index.html) and click on the "graph" link to the left of the dataset named "PIFSC CTD Data".

This form allows you to plot a subset of the CTD data that was collected over a number of cruises, using a set of constraints.

Let's look at cruise "HA1101".

* In the first row of the "Constraints" column, select the variable "LEG\_NAME" using the drop down menu.
* Under "Optional constraint \#1", another drop down menu appears, allowing you to select specific cruise legs. Select "HA1101\_LEG\_I".
* Add a second constraint, to look at depths \("DEPTH\_SW\_M"\) shallower than 20m.
* Set the color scale to reflect water temperature by selecting the "Temperature" variable in "Color", under "graph type".
* click on "redraw graph".

![](../.gitbook/assets/image%20%2820%29.png)

Let's now make a traditional temperature/salinity plot:

* Below "graph type", select "salinity" as the "X Axis", and "temperature" as the "Y Axis", and "DEPTH\_SW\_M" as the "Color".
* Remove the depth constraint by select the blank space at the top of the drop down menu
* Under "Graph settings", select "circle" as the marker type, white as the "color", and set the color bar maximum to 600 \(that is about the maximal depth in the dataset\)
* click on "redraw graph"

![](../.gitbook/assets/image%20%2866%29.png)

## Example \#3. Look at wind data from Hurricane Katrina

Go to the [OceanWatch Central Pacific ERDDAP](https://oceanwatch.pifsc.noaa.gov/erddap/index.html) and click on the "graph" link to the left of the dataset named " Ocean Surface Winds, QuikSCAT - 3-Day, 1999-2009".

* Click on the "graph" link to the left of the dataset
* Change the region to 10-40N, 260-300E
* Change the date to 08/26/2005
* click on "redraw graph"

![](../.gitbook/assets/image%20%2879%29.png)

* Change the "Graph Type" to "vectors"
* Change "Vector X" to "ux" and "Vector Y" to "vy"

![](../.gitbook/assets/image%20%28109%29.png)

## Example \#4. Examine the 1998 El Niño

Go to the [OceanWatch Central Pacific ERDDAP](https://oceanwatch.pifsc.noaa.gov/erddap/index.html) and click on the "graph" link to the left of the dataset named "Sea Surface Temperature, Coral Reef Watch, CoralTemp - Monthly, 1985-present".

* Make a map of SST for January 1997, for the region: -20 - 20N, 180 to 300E, and adjust the color scale to 18-30ºC
* Click on "Redraw the Graph"

![SST for January 1997](../.gitbook/assets/image%20%28128%29.png)

* Make a map of SST for January 1998, for same region and adjust the color scale
* Click on "Redraw the Graph"

![](../.gitbook/assets/image%20%28166%29.png)

We can clearly see the tongue of warm water due to the 1998 El Niño.

Now let's make a **Hovmöller plot**: 

* Below "Graph Type", select "time" in the drop down menu for "Y Axis". 
* Adjust the date range to jan. 1995 - Dec. 2000 
* Adjust the latitude to 0º, and the longitude to 180 to 300º
* Adjust the color scale to 18-30ºC
* Click on "Redraw the Graph"

![](../.gitbook/assets/image%20%2875%29.png)

Again, the winter of 1998 was clearly anomalous compared to other years.

## Understanding the URL generated by ERDDAP

Do you have a graph you like? Want to save it or send it to someone? Change the drop-down menu next to “set the File Type” to png and click on “download the data”, that will create a png file with just that image in it. 

You can copy the url and send it to someone which will recreate the image. The url can also be edited. 

We’ll walk through some examples using the url created in Example \#1:

[https://oceanwatch.pifsc.noaa.gov/erddap/griddap/aqua\_chla\_8d\_2018\_0.graph?chlor\_a\[\(2018-06-02T12:00:00Z\)\]\[\(23.02083\):\(18.02083\)\]\[\(200.0208\):\(208.0208\)\]&.draw=surface&.vars=longitude%7Clatitude%7Cchlor\_a&.colorBar=%7C%7C%7C0.005%7C%7C&.bgColor=0xffffffff](https://oceanwatch.pifsc.noaa.gov/erddap/griddap/aqua_chla_8d_2018_0.graph?chlor_a[%282018-06-02T12:00:00Z%29][%2823.02083%29:%2818.02083%29][%28200.0208%29:%28208.0208%29]&.draw=surface&.vars=longitude%7Clatitude%7Cchlor_a&.colorBar=%7C%7C%7C0.005%7C%7C&.bgColor=0xffffffff)

* Base ERDDAP URL:

  `https://oceanwatch.pifsc.noaa.gov/erddap/griddap/`  

* Dataset ID: `aqua_chla_8d_2018_0`  We could use aqua\_chla\_monthly\_2018\_0 instead. 
* File type: `.graph`
  * Changing `graph` to `png` or `largePng` will create a png file of the image 
  * Changing `graph` to `csv` will download a CSV file to your computer.  A complete list of the available file format options can be viewed in the dropdown menu next to “Set the File Type”
  * Changing `graph` to `html` will bring up the form to download the data  
* Variable name: `chlor_a`  Some datasets contain several variables. For example, wind data typically has a wind speed variable, a u-component variable and a v-component variable.  
* Time: `[(2018-06-02T12:00:00Z)]`
  * Changing the date to last will ensure the graph always plots the most recent data  
* Latitude range: `[(23.02083):(18.02083)]` 
* Longitude range: `[(200.0208):(208.0208)]` 
*  Everything beginning with `&.draw` adjusts the look of the image `&.draw=surface&.vars=longitude%7Clatitude%7Cchlor_a&.colorBar=%7C%7C%7C0.005%7C%7C&.bgColor=0xffffffff`

## Example \#5. On your own. Chlorophyll time series

* First, create a map of a monthly composite of AQUA MODIS chlorophyll concentration around Hawaii for the date of your choice. 
* Create a time series of monthly chlorophyll concentration for a location close to Honolulu.  Hint: you will need to change the "Graph Type". Make sure to select of few years worth of data. Make sure your longitude is within the correct range and your latitudes in the correct order
* If there are gaps or outlier values, try again for a location further south \(i.e. slightly further from the coast and shallow water\) 
* Do you see any seasonal variation? 
* Download the time series data as a .csv file 
* Select a date for a period of low chlorophyll and create a map in a new browser window for that date 
* Open a new browser window, copy and paste the URL for the first map and create a map for a period of high chlorophyll by changing only the date in the URL 
* Compare the two maps and save them as .png

## Downloading the data

You can easily download any of the data on ERDDAP in a variety of different formats: .ncdf, .mat, .asc, etc. 

To the left of any dataset on the main ERDDAP page, click on “data” instead of "graph".   
ERDDAP generates a Data Access Form, where you can specify constraints to get the data you need: time range, latitude range, longitude range, altitude, data variables, and file type. You can then access the resulting data file via a URL, or use the Submit button to download the file to your computer. 

If you are making a graph of the data \(on the page that says “Make A Graph”\) just click on the “Data Access Form” link above the graph. You can also access this form by replacing the “.graph” in the url with “.html”.

## Using ERDDAP URLs in your software application

ERDDAP URL’s can be used to directly access data in any application, programming language or scripting language that can send a URL and receive a file \(such as Python, Java, php, JavaScript, shell scripts using “curl” or “wget”\), as well as from OPeNDAPenabled applications clients such as R, Matlab, GrADS, Ferret, and IDL. 

Many programming and scripting languages such as Java, python, php, and JavaScript can manipulate ERDDAP URL’s to import data for research or modeling, or for use in dynamic web pages.





