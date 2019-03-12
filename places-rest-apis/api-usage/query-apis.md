# Query APIs

On a GET call, with the following input, the service returns the closest POIs to the caller:

* The caller's position \(latitude, longitude\).
* The IDs of the POI libraries to be included in the search.
* The maximum number of POIs to return.  The default value is 100. 

 The distance between the caller and POI is defined as the distance from the caller to the edge of the POI's geofence. In the response, POIs that contain the caller will be marked as having the caller.

Arguments need to be supplied as the following query parameters:

* \(**Required**\) Latitude: caller's latitude. -85 &lt;= latitude &lt;= 85.  
* \(**Required**\) Longitude: caller's longitude. -180 &lt;= longitude &lt;= 180. 
* \(**Optional**\) Limit: max number of POIs to return. Optional. 
* \(**Required**\) Library: id of library to query. Include multiple library query params to query multiple libraries. 

On success, returned JSON format is as follows:

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

 POIs under `places.pois` are sorted by distance from caller to the edge of the POIs. POIs under places.userWithin contains the caller. They are ordered first by rank, then by increasing radius.

