# Places UI

POIs and libraries are created and managed in the Places database by using the Places UI. 

## Size and reliability 

Size and reliability are important for geofences that are being used in region monitoring from a mobile app regardless of whether Adobe Place or some other service is used. Operating systems recommend some parameters to keep in mind when creating geofences. For maximum reliability, geofences should have a radius of at least 100 meters. You can create smaller geofences, but entry and exit events might not be generated, or might be generated after the user stops moving for a period. 

In addition, accuracy and reliability might be reduced based on hardware conditions such as wi-fi being turned off or unavailable and also on the device's location in relation to hampering GPS signals. For example, mountainous areas, urban settings, and indoor areas can reduce location accuracy from iOS and Android.  



