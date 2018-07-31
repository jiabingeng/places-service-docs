# Locations

* POIs’ geofence: support circle only for now.
* Defined by a center point in latitude, longitude + radius in meters. 20m&lt;radius&lt;2000m to alleviate privacy concerns.
* POI’s country/state/city/street info. We don’t cross check this info with the POI’s geofence info, so it’s a good idea for the customer to make sure they are accurate, for example by deriving the geofence using a geo-location service like Google Maps API.

