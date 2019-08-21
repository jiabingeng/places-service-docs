# Manage POIs in the Places UI

## Defining a geofence POI

Geofences are a type of POI and are defined in the database based by the following keys:

| Keys | Description | Required? |
| :--- | :--- | :--- |
| ID | Unique identifier assigned to each POI | Yes |
| Name | Friendly Name given to the POI | Yes |
| Library | Each POI must be assigned a library for organization | Yes |
| Icon | Assist with visualizations of the POIs | Yes \(assigned default\) |
| Color | Assist with visualizations of the POIs | Yes \(assigned default\) |
| Category | Assign a common framework of categories that are common across all POIs in all libraries | No |
| Address | Street address | No |
| City | city of POI | No |
| State/Region | state or region of POI | No |
| Country | country of POI | No |
| Latitude | Latitude coordinate for center of POI | Yes |
| Longitude | Longitude coordinate for center of POI | Yes |
| Metadata | custom key + value pairs that can be assigned to POIs. This metadata streamlines future workflows by allowing you to group POIs across libraries for each to use rules and filters in downstream workflows such as send a push notification whenever someone enter a POI with Type = Competitor. | No |

## Create a POI

A point of interest \(POI\) is a location or a point on a map that is of interest to you. It can include locations like cafes, restaurants, and so on.

1. Log in to Adobe Places with your Adobe ID.
2. In the top right side, click the icon that looks like a bulleted list and then click  **New**.  This step displays all of the POIs in your library.
3. In the map view, on the lower right side, click **+ New POI**. 
4. Type a name for your POI.
5. Select or add a library.
6. Enter or select a radius.

   a. Select an icon for your POI.

   b. Select a color for the icon.

7. Expand the **Location** section.

   a. Type an address.

   b. Type the city.

   c. Type the name of the state.

   d. Type the name of the country.

   e. Select or enter a latitude or longitude.

   f. Click **Drop Pin on Map**.

8. Expand the **Metadata** section and click **Add Metadata.**

   a. Type the key name.

   b. Type the key value.

9. Click **Confirm** and then **Save**.

## Edit a POI

1. Log into Adobe Places Service using your Adobe ID.
2. In the top right side, click the icon that looks like a bulleted list.
3. Locate the POI that you want to edit.
4. Click **...** and select **View Details**.
5. Update the information and click **Save**

## Delete a POI

1. Log into Adobe Places Service using your Adobe ID.
2. In the top right side, click the icon that looks like a bulleted list.
3. Locate the POI that you want to delete.
4. Click **...** and select **Delete**.

## Filter POIs by city, state, country, or metadata

1. Log into Adobe Places Service using your Adobe ID.
2. In the top right side, click the filtering icon.
3. You can filter POIs in one of the following ways: 
4. By library:

   a. Select a library.

5. By property:

   a. In **Property** drop-down list, select **Country**, **State**, or **City**.

   b. In the next line, enter a value. For example, you can select **State** and type **California**.

6. With metadata:

   a. Enter a key and value.

