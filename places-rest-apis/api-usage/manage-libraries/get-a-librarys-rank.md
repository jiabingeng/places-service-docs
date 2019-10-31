# Get a library's rank

**Important**: This content has permanently moved to [https://docs.adobe.com/content/help/en/places/using/web-service-api/api-usage/manage-libraries/get-a-librarys-rank.html](https://docs.adobe.com/content/help/en/places/using/web-service-api/api-usage/manage-libraries/get-a-librarys-rank.html), so that it can be in the same place as other Adobe Experience Cloud content and be translated into several languages.

Please update your bookmarks.

A GET method that allows you to rank libraries.

## Request

`GET https://api-places.adobe.io/places/placesapi/v1/libraries/rank`

## Headers

`-H Content-Type: application/JSON    
-H 'Authorization: Bearer <TOKEN>'    
-H 'x-api-key: <API KEY>'    
-H 'x-gw-ims-org-id: <ORGID>'    
-H 'Accept-Language: en-US'`

## Sample response

`{"library_rank_order":["ea45781f-26af-44b1-b4f8-43baf5f0fe28","dfcc5270-1d6d-4bc9-9cd9-85ecd5ebc12b"]}`

## CURL command

`curl -X GET 'https://api-places.adobe.io/places/placesapi/v1/libraries/rank ' -H 'x-api-key: <API KEY>' -H 'Authorization: Bearer <TOKEN>' -H 'x-gw-ims-org-id: <ORGID>'`

**Important**: Replace variables such as `<API KEY>`, `<TOKEN>`, and `<ORGID>` with actual values.

