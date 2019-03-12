# Query APIs

A GET method that allows you to query the POIs that are closest to the caller.

## Request

```text
GET https://query.places.adobe.com/placesedgequery
```

With the following input, the service returns a list of the POIs that are closest to the caller:

* The caller's position \(latitude, longitude\).
* The IDs of the POI libraries to be included in the search.
* The maximum number of POIs to return.  The default value is 100. 

 The distance between the caller and POI is defined as the distance from the caller to the edge of the POI's geofence. In the response, POIs that contain the caller will be marked as having the caller.

Arguments need to be supplied as the following query parameters:

* \(**Required**\) Latitude: caller's latitude, which must be between -85 and 85.  
* \(**Required**\) Longitude: caller's longitude, which must be between -180 and 180. 
* \(**Optional**\) Limit, which is the maximum number of POIs to return.  
* \(**Required**\) Library,  which is the ID of the library to query.  This parameter includes multiple library query parameters to query multiple libraries. 

Here is an example of the successful returned JSON format:

```markup
{
    "places": {
        "userWithin": [
            {
                "p": [
                    "poi id",
                    "poi name",
                    "poi center's latitude",
                    "poi center's longitude",
                    poiRadius,
                    rank
                ],
                "x": {
                    "country": "US",
                    "city": "Fremont",
                    "street": "Vineyard Heights",
                    "Color": "Blue",
                    "state": "CA",
                    <other POI metadata>
                }
            }
        ],
        "pois": [
            {
                "p": [
                    "poi id",
                    "poi name",
                    "poi center's latitude",
                    "poi center's longitude",
                    poiRadius,
                    rank
                ],
                "x": {
                    "country": "US",
                    "city": "Milpitas",
                    "street": null,
                    "state": "CA"
                }
            },
            {
                "p": [
                    "poi id",
                    "poi name",
                    "poi center's latitude",
                    "poi center's longitude",
                    poiRadius,
                    rank
                ],
                "x": {
                    "country": "US",
                    "city": "Fremont",
                    "street": null,
                    "state": "CA"
                }
            }
        ]
    }
}
```

 POIs under `places.pois` are sorted by distance from caller to the edge of the POIs. POIs under `places.userWithin` contains the caller, and these POIs are ordered by rank and then by increasing radius.

