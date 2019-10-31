# Custom Places objects

{% hint style="warning" %}
This content has permanently moved to [https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-extension/cust-places-objects.html](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-extension/cust-places-objects.html), so that it can be in the same place as other Adobe Experience Cloud content and be translated into several languages.

Please update your bookmarks.
{% endhint %}

Here are the custom native classes that will be used with the Places APIs:

{% tabs %}
{% tab title="iOS" %}
### ACPPlacesPoi

Here is the definition:

```text
/**
 *  @class ACPPlacesPoi
 *
 *  This class contains data that is directly correlated to the properties maintained by the Adobe Places Database.
 */
@interface ACPPlacesPoi : NSObject

@property (nonatomic, strong, nullable) NSString* identifier;  ///< The identifier for the POI
@property (nonatomic, strong, nullable) NSString* name;  ///< The name of the POI
@property (nonatomic) double latitude;  ///< The latitude of the POI's center
@property (nonatomic) double longitude;  ///< The longitude of the POI's center
@property (nonatomic) NSUInteger radius;  ///< The radius of the POI
@property (nonatomic, strong, nullable) NSDictionary<NSString*, NSString*>* metaData;  ///< Dictionary containing meta data for the POI
@property (nonatomic) Boolean userIsWithin;  ///< Indicates if the device is currently inside of this POI

@end
```
{% endtab %}
{% endtabs %}

