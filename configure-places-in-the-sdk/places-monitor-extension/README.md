# Places Monitor extension

{% hint style="warning" %}
This content has permanently moved to [https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-monitor-extension/places-monitor-extension.html](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-monitor-extension/places-monitor-extension.html), so that it can be in the same place as other Adobe Experience Cloud content and be translated into several languages.

Please update your bookmarks.
{% endhint %}

The Places Monitor extension handles the interactions with the operating system to register and monitor the POIs that are closest to the user. This extension retrieves the POIs that need to be registered from the Places extension and passes the entry and exit notifications to the Places extension. These notifications will be available in Experience Platform Launch rules as events.

The Monitor extension is optional, because some customers might already be monitoring regions with the operating system. If this is the case, ensure that you add the Places extension APIs to receive the nearest POIs from the Places database and to also pass the entry and exit events so that the appropriate actions can be taken.

