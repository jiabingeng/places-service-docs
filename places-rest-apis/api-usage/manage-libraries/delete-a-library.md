# Delete a library

{% hint style="warning" %}
This content has permanently moved to [https://docs.adobe.com/content/help/en/places/using/web-service-api/api-usage/manage-libraries/delete-a-library.html](https://docs.adobe.com/content/help/en/places/using/web-service-api/api-usage/manage-libraries/delete-a-library.html), so that it can be in the same documentation system as other Adobe Experience Cloud content and be automatically translated into several languages.

Please update your bookmarks.
{% endhint %}

A DELETE method that lets you delete a library.

## Request

```text
DELETE https://api-places.adobe.io/places/placesapi/v1/libraries/<lIBRARYID>
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

Use the following CURL command to test this API:

```text
curl -X DELETE 'https://api-places.adobe.io/places/placesapi/v1/libraries/<LIBRARYID>' -H 'x-api-key: <API KEY>' -H 'Authorization: Bearer <TOKEN>' -H 'x-gw-ims-org-id: <ORGID>'
```

**Important**: Replace variables such as `<lIBRARYID>`, `<API KEY>`, `<TOKEN>`, and `<ORGID>`with actual values.

