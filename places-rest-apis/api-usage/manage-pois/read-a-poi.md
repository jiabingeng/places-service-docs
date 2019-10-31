# Read a POI

{% hint style="warning" %}
This content has permanently moved to [https://docs.adobe.com/content/help/en/places/using/web-service-api/api-usage/manage-pois/read-a-poi.html](https://docs.adobe.com/content/help/en/places/using/web-service-api/api-usage/manage-pois/read-a-poi.html), so that it can be in the same place as other Adobe Experience Cloud content and be translated into several languages.

Please update your bookmarks.
{% endhint %}

A GET method that returns the details for a POI.

## Request

```text
GET https://api-places.adobe.io/places/placesapi/v1/pois/<POIID>
```

## Headers

```text
-H' Content-Type: application/json'  
-H 'Authorization: Bearer <TOKEN>'  
-H 'x-api-key: <API KEY>'  
-H 'x-gw-ims-org-id: <ORGID>'  
-H 'Accept-Language: en-US'
```

## Sample Response

```text
{
    "id": "66e3c0fb-12fe-4af2-863e-16e0e578d777",
    "name": "Train Station Road",
    "description": "18827",
    "location": {
        "type": "Point",
        "coordinates": [
            -121.902498,
            37.331087
        ]
    },
    "radius": 66,
    "country": "PH",
    "state": "41",
    "city": "Quezon City",
    "street": "No. 10 Train Station Road",
    "category": "",
    "icon": "",
    "color": "",
    "metadata": {
        "ownership": "LS",
        "brand": "Train station"
    },
    "lib_id": "6efd87bc-c9c4-4ff3-9503-051bfbc81777"
}
```

## CURL command

Use the following CURL command to test the API:

```text
curl -X GET 'https://api-places.adobe.io/places/placesapi/v1/pois/<POIID>' -H 'x-api-key: <API KEY>' -H 'Authorization: Bearer <TOKEN>' -H 'x-gw-ims-org-id: <ORGID>'
```

**Important**: Replace `<POIID>`, `<API KEY>`, `<TOKEN>`, and `<ORIGIN>` with actual values.

