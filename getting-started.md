# Getting started

## Get provisioned to use Adobe Places

Places requires special provisioning context with your regular Adobe Experience Platform provisioning context. 

To get provisioned, complete the following tasks:

* In the Admin Console, ensure that your organization is provisioned with Places.  If you are not the Adobe administrator, contact the administrator to ensure the Places context in Admin Console.
* Ensure you are listed as a user under the Places and Launch product contexts in the Admin Console. For more information, see Adding a user to Launch and Places.
* Ensure your mobile app property is configured in Adobe Launch with the Places extension installed.  For more information, see [Adobe Places \(Beta\)](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/places-extension-1). 
* If your company has multiple Adobe organizations, ensure that you always select the organization that is provisioned for Places. This allows you to add your POIs and Libraries.

To help you complete a batch import of your POIs from a `.csv` file into your organization's Places database, we created a set of Python scripts. You can download the zip file of these scripts [here](https://github.com/adobe/places-scripts). For instructions on how to use the scripts, see the included README file.

## Understanding the Places UI

To access the Places UI, in a browser, go to [ https://places.adobe.com](%20https://places.adobe.com) and log in with your Adobe ID. 

Here is some basic information to help you get familiarized with the UI:

* In the upper right corner of the screen, there are buttons for zooming in and out, centering on your current location \(**Find Me**\), and switching between the map view and satellite view.
* Double click to zoom in or click and drag to recenter the map.
* You can also use the arrow keys to scroll the map
* In the lower right corner, click the New Poi button to create a new point of interest \(POI\).

![](.gitbook/assets/places_ui_intro.png)

## Creating libraries and POIs

You can create libraries and POIs in one of the following ways:

* By using the web services. For more information, see Places web services.
* By using the Places UI. For more information, see Places UI. 

## Create an empty library in the Places database by using the Places UI

1. Log into Adobe Places UI \(The user interface to visually add and manage the POIs and libraries\). 
2. Click on the **Libraries** tab.
3. Click **Create Library**.
4. Type the name.
5. Click **Confirm**.

## Create a new POI in the library by using the Places UI

A point of interest \(POI\) is a location or a point on a map that is of interest to you. It can include locations like cafes, restaurants, and so on.

1. Log in to Adobe Places UI, in a browser, type [https://places.adobe.com](https://places.adobe.com).
2. In the top left side, click **Map**.
3. In the map view, on the lower right side, click **+ New POI**. 
4. Expand the **Details** section.
5. Type a name.
6. Select a library.
7. Enter or select a radius. 
8. Select the icon that you want to use for your POI.
9. Select a color for your POI icon.
10. Type a category.
11. Expand the **Location** section.
12. Type an address.
13. Type the city.
14. Type the name of the state.
15. Type the name of the country.
16. Select or enter a latitude or longitude.
17. Click **Drop Pin on Map**.
18. Expand the **Metadata** section and click **Add Metadata.**
19. **Type the key name.**
20. **Type the key value.**
21. Click **Confirm**.

