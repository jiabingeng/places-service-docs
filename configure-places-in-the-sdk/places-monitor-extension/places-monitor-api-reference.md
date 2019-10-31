# Places Monitor API reference

{% hint style="warning" %}
This content has permanently moved to [https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-monitor-extension/places-monitor-api-reference.html](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-monitor-extension/places-monitor-api-reference.html), so that it can be in the same place as other Adobe Experience Cloud content and be translated into several languages.

Please update your bookmarks.
{% endhint %}

## Register Places Monitor Extension

Registers the Places Monitor extension with the Core Event Hub.

{% tabs %}
{% tab title="Android" %}
### RegisterExtension

#### Syntax

```java
public static void registerExtension();
```

#### Example

Call this method in the `onCreate` method where you initialize the rest of the Experience Platform SDK.

```java
public class MobileApp extends Application {
  @Override
  public void onCreate(){
     super.onCreate();
     MobileCore.setApplication(this);
     try {
        PlacesMonitor.registerExtension();
     } catch (Exception e) {
       //Log the exception
       }
    }
 }
```
{% endtab %}

{% tab title="iOS" %}
### RegisterExtension

#### Syntax

```objectivec
+ (void) registerExtension;
```

#### Example

This method should be called in the `didFinishLaunchingWithOptions` delegate method of the `AppDelegate`.

```objectivec
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {

    [ACPCore configureWithAppId:@"launch-appID"];    
    [ACPPlaces registerExtension];    
    [ACPPlacesMonitor registerExtension];

    [ACPCore start:^{
        // do other initialization of the SDK
    }];

    return YES;
}
```
{% endtab %}
{% endtabs %}

## Extension version

Returns the current version of the Places Monitor extension

{% tabs %}
{% tab title="Android" %}
### ExtensionVersion

#### Syntax

```java
public static String extensionVersion();
```

#### Example

```java
String placesMonitorVersion = PlacesMonitor.extensionVersion();
```
{% endtab %}

{% tab title="iOS" %}
### ExtensionVersion

#### Syntax

```objectivec
+ (nonnull NSString*) extensionVersion;
```

#### Example

```objectivec
NSString *placesMonitorVersion = [ACPPlacesMonitor extensionVersion];
```
{% endtab %}
{% endtabs %}

## Start device monitoring

Begin tracking the device's location and monitoring nearby Places.

{% tabs %}
{% tab title="Android" %}
### Start

If authorization to use device location has not been granted by the user, the first call to the `start` API prompts the user for permission.

#### Syntax

```java
public static void start();
```

#### Example

```java
PlacesMonitor.start();
```
{% endtab %}

{% tab title="iOS" %}
### Start

**Important**: To begin monitoring, the location service must have the necessary authorization.

* If the authorization for the location service has not been provided to the application, the first call to the `start` API requests the authorization to use the location service as configured for the application.
* Depending on your device's capabilities, if the authorization has been provided, the Places Monitor tracks the user's location based on the currently set `ACPPlacesMonitorMode`. By default, the monitor uses `ACPPlacesMonitorModeSignificantChanges`.

{% hint style="warning" %}
If your call to start monitoring is made before the SDK has finished initializing, it may be ignored.

You can ensure the SDK has finished initialization by calling `start` from the callback provided to `ACPCore::start:`.
{% endhint %}

#### Syntax

```objectivec
+ (void) start;
```

#### Example

Starting the Places Monitor when the SDK is initializing:

```objectivec
[ACPCore start:^{
    [ACPPlacesMonitor start];
}];
```

Starting the Places Monitor later in app execution:

```objectivec
[ACPPlacesMonitor start];
```
{% endtab %}
{% endtabs %}

## Stop device monitoring

Calling this method will stop tracking the customer's location. It will also unregister all previously registered regions. Optionally, you can purge client-side data by passing in `YES` for the clearData parameter. When you call this method with `YES` for clearData purges the data even if the monitor is not actively tracking the device's location.

{% tabs %}
{% tab title="Android" %}
### Stop

#### Syntax

```java
public static void stop(final boolean clearData);
```

#### Example

```java
PlacesMonitor.stop(true);
```
{% endtab %}

{% tab title="iOS" %}
### Stop

#### Syntax

```objectivec
+ (void) stop: (BOOL) clearData;
```

#### Example

```objectivec
[ACPPlacesMonitor stop:YES];
```
{% endtab %}
{% endtabs %}

## Update Location

Use this API for an immediate update on the device's location. When you call this API, the device attempts to determine the location with the level of accuracy that you specified. This process also refreshes the nearby POIs that are monitored by the extension.

{% tabs %}
{% tab title="Android" %}
### UpdateLocation

#### Syntax

```java
public static void updateLocation();
```

#### Example

```java
PlacesMonitor.updateLocation();
```
{% endtab %}

{% tab title="iOS" %}
### UpdateLocationNow

#### Syntax

```objectivec
+ (void) updateLocationNow;
```

#### Example

```objectivec
[ACPPlacesMonitor updateLocationNow];
```
{% endtab %}
{% endtabs %}

## Monitoring Mode \(iOS only\)

Monitoring can be set to one of the following values:

* `ACPPlacesMonitorModeContinuous`

  The monitoring extension receives and processes locations more frequently. This monitoring strategy consumes a lot of power but provides higher accuracy. For more information, see [Apple documentation on continuous monitoring](https://developer.apple.com/documentation/corelocation/cllocationmanager/1423750-startupdatinglocation).

* `ACPPlacesMonitorModeSignificantChanges`

  The monitoring extension only receives and processes location updates after the device has moved a significant distance from the previously processed location. This monitoring strategy consumes less power than the continuous monitoring strategy. For more information, see [Apple documentation on significant monitoring](https://developer.apple.com/documentation/corelocation/cllocationmanager/1423531-startmonitoringsignificantlocati)

{% tabs %}
{% tab title="iOS" %}
### SetPlacesMonitorMode

#### Syntax

```objectivec
+ (void) setPlacesMonitorMode: (ACPPlacesMonitorMode) monitorMode;
```

#### Example

```objectivec
[ACPPlacesMonitor setPlacesMonitorMode:ACPPlacesMonitorModeSignificantChanges];
```
{% endtab %}
{% endtabs %}

