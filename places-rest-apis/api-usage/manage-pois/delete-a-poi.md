# Delete a POI

{% hint style="warning" %}
This content has permanently moved to [https://docs.adobe.com/content/help/en/places/using/web-service-api/api-usage/manage-pois/delete-a-poi.html](https://docs.adobe.com/content/help/en/places/using/web-service-api/api-usage/manage-pois/delete-a-poi.html), so that it can be in the same documentation system as other Adobe Experience Cloud content and be automatically translated into several languages.

Please update your bookmarks.
{% endhint %}

A DELETE method that lets you delete a POI.

## Request

```text
DELETE https://api-places.adobe.io/places/placesapi/v1/pois/<POIID>
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
If successful a Status of "204 No Content" is returned.
```

## CURL command

Use the following CURL command to test the API:

```text
curl -X DELETE 'https://api-places.adobe.io/places/placesapi/v1/pois/<POIID>' -H 'x-api-key: <API KEY>' -H 'Authorization: Bearer <TOKEN>' -H 'x-gw-ims-org-id: <ORGID>'
```

**Important**: Replace `<POIID>`, `<API KEY>`, `<TOKEN>`, and `<ORGID>` with actual values.

