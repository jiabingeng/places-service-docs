# Using the Places Monitor extension

## Install the Places Monitor extension in Experience Platform Launch  <a id="configure-places-monitoring-extension-in-launch"></a>

1. In Experience Platform Launch, click the **Extensions** tab.
2. On the **Catalog** tab, locate the **Places Monitor** extension, and click **Install**.
3. Click **Save**.
4. Follow the publishing process to update the SDK configuration.

‌

### **Configure the Places Monitor extension**  <a id="configure-places-extension"></a>

There are no configuration tasks for the Places Monitor extension.![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-Lf1Mc1caFdNCK_mBwhe%2F-Lf1N06T8hdv0-r5jPPN%2F-Lf1ND5ZuVvkxT6j2GiQ%2Fconfigure_places_monitor.png?generation=1558039292942097&alt=media)‌

## Add the Places Monitor extension to your app  <a id="add-places-monitor-extension-to-your-app"></a>

{% tabs %}
{% tab title="Android" %}
This content is currently in progress.
{% endtab %}

{% tab title="iOS" %}
1. Add the library to your project via your Cocoapods `Podfile` by adding `pod 'ACPPlacesMonitor'`.
2. Import the Places and Places Monitor libraries:

#### Objective-C  <a id="objective-c"></a>

```objectivec
#import "ACPCore.h"#import "ACPPlaces.h"#import "ACPPlacesMonitor.h"
```

#### Swift  <a id="swift"></a>

```swift
import ACPPlacesimport ACPPlacesMonitor
```
{% endtab %}
{% endtabs %}

## Register the Places Monitor with Mobile Core <a id="register-the-places-monitor-with-mobile-core"></a>

{% tabs %}
{% tab title="Android" %}
This content is in progress.
{% endtab %}

{% tab title="iOS" %}
In your app's`application:didFinishLaunchingWithOptions`, register `PlacesMonitor` and Places with Mobile Core:

#### Objective-C  <a id="objective-c-1"></a>

```objectivec
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:                  (NSDictionary*)launchOptions {    [ACPCore configureWithAppId:@"yourAppId"];    [ACPPlaces registerExtension];    [ACPPlacesMonitor registerExtension];     [ACPCore start:^{            // do other initialization required for the SDK            }];     return YES; }
```

#### Swift  <a id="swift-1"></a>

```swift
func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {       ACPCore.configure(withAppId: "yourAppId")          ACPPlaces.registerExtension()       ACPPlacesMonitor.registerExtension()       ACPCore.start(nil)       // Override point for customization after application launch.        return true}
```

**Important**: Places monitoring depends on the Places extension. When manually installing the Places Monitor extension, ensure that you also add the `libACPPlaces_iOS.a` library to your project.
{% endtab %}
{% endtabs %}

## Add permissions to the manifest <a id="add-permissions-to-the-manifest"></a>

{% tabs %}
{% tab title="Android" %}
**Java**

For all versions of Android, to declare that your app need location permission, put a `<uses-permission>` element in your app manifest, as a child of the top-level `<manifest>` element.

```java
<manifest xmlns:android="http://schemas.android.com/apk/res/android"        package="com.adobe.placesapp">​      <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />​    <application ...>        ...    </application></manifest>
```
{% endtab %}

{% tab title="iOS" %}
This content is in progress.
{% endtab %}
{% endtabs %}

## Enable location updates in the background  <a id="enable-location-updates-in-background"></a>

iOS supports the delivery of location events to apps that are suspended or no longer running. To receive location updates in the background for the Places Monitor extension, configure the Location updates capability for your app in `Xcode.background-location-updates`.![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-Lf1Mc1caFdNCK_mBwhe%2F-Lf1N06T8hdv0-r5jPPN%2F-Lf1ND5l_pAVGYilVYrd%2Fusing-the-places-monitor_1.png?generation=1558039292115216&alt=media)

## Configuring the plist keys  <a id="configuring-the-plist-keys"></a>

You must include the `NSLocationWhenInUseUsageDescription` and `NSLocationAlwaysAndWhenInUseUsageDescription` keys in your app's `Info.plist` file. If the keys are not present, the authorization requests fail immediately.

**Important**: If your app supports iOS 10 and earlier, the `NSLocationAlwaysUsageDescription` key is also required.

* `NSLocationWhenInUseUsageDescription` should be added with the value describing why the app is requesting access to the user’s location information while running in the foreground.
* `NSLocationAlwaysAndWhenInUseUsageDescription` should be added with the describing why the app is requesting access to the user’s location information at all times.

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-Lf1Mc1caFdNCK_mBwhe%2F-Lf1N06T8hdv0-r5jPPN%2F-Lf1ND5n5T7duUiuf86T%2Fusing-the-places-monitor_2.png?generation=1558039291984718&alt=media)

