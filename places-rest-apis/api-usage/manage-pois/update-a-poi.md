# Update a POI

**Important**: This content has permanently moved to [https://docs.adobe.com/content/help/en/places/using/web-service-api/api-usage/manage-pois/update-a-poi.html](https://docs.adobe.com/content/help/en/places/using/web-service-api/api-usage/manage-pois/update-a-poi.html), so that it can be in the same place as other Adobe Experience Cloud content and be translated into several languages.

Please update your bookmarks.

A PUT method that lets you update a POI.

## Request <a id="request"></a>

```text
PUT https://api-places.adobe.io/places/placesapi/v1/pois/<POIID>
```

## Headers <a id="headers"></a>

```text
-H' Content-Type: application/json'  -H 'Authorization: Bearer <TOKEN>'  -H 'x-api-key: <API KEY>'  -H 'x-gw-ims-org-id: <ORGID>'  -H 'Accept-Language: en-US'
```

## Body <a id="body"></a>

```text
{  "id": "string",  "name": "string",  "description": "string",  "location": {    "type": Point",    "coordinates": [<LONGITUDE>, <LATITUDE>]  },  "radius": 0,  "country": "string",  "state": "string",  "city": "string",  "street": "string",  "category": "string",  "icon": "string",  "color": "string",  "metadata": {          "brand": "string",          "owndership": "string"          },  "lib_id": "{libraryID}"}
```

## Sample Response <a id="sample-response"></a>

```text
{    "id": "66e3c0fb-12fe-4af2-863e-16e0e777d777",    "name": "New Name",    "description": "18827",    "location": {        "type": "Point",        "coordinates": [            -123.000507,            37.698029        ]    },    "radius": 66,    "country": "US",    "state": "CA",    "city": "Small City",    "street": "1 Island Road",    "category": "",    "icon": "",    "color": "",    "metadata": {        "ownership": "LS",        "brand": "Island station"    },    "lib_id": "6efd87bc-c9c4-4ff3-9503-051bfbc81777"}
```

## CURL command <a id="curl-command"></a>

Use the following CURL command to test this API:

```text
curl -X PUT 'https://api-places.adobe.io/places/placesapi/v1/pois/<POIID>' -H 'x-api-key: <API KEY>' -H 'Authorization: Bearer <TOKEN>' -H 'x-gw-ims-org-id: <ORGID>' -d '<SINGLEPOIDATA>' -H "Content-Type: application/json"
```

**Important**: Replace `<POIID>`, `<API KEY>`, `<TOKEN>`, `<ORGID>`, and `<SINGLEPOIDATA>` with actual values.

