# Overview

Places is the set of services that makes it easier for Adobe customers to hydrate the Adobe Cloud Platform and Adobe Experience Cloud solutions with location data, delivering the right experience to the right person at the right time and the right place.

Places comprises the following components:

* The Places library, which creates and manages Places across properties.
* The SDK Monitoring Extension, which tracks the location movement of users.
* Places rules, which takes the appropriate actions from the location data.

The goal of Places is to fuse the physical and digital worlds by doing the following:

* Manage Geofences
* Measure location of users even when app is in the background
* Use data in real-time when it matters 

For example, you can send a personalized notification when user enters one of your stores, send link to a satisfaction survey _x_ hours after this user visited one of your stores in San Francisco, and so on.

## Key Features

* Geospatial POI query

  Services to provide POI \(Points of Interest\) within an area \(used by Mobile SDK\)

* Configuration of Places Extension

  Services and UI to control Places settings such as selection of Library for use by a specific App

* POI Database Management

  Services and UI to add/remove/display POIs within a Library

* Rules engine support

  Services and UI to support Places/POI data while creating Mobile SDK rules

* SDK: Utilize Geospatial POI query

  Provide parity with v4 location capabilities, but with just local POIs being queried from the geospatial query API based on grid location of the device

* SDK: Location monitoring

  Monitoring user lat and long from OS

## Benefits

Here are the key benefits to using Places:

* Deliver the right message or experience to users in real time at the instant it is relevant to them and where they are.
* Target messages and experiences to their users based on their historical interactions with places 
* Gain deeper insights into their users by analyzing their physical behavior
* Attribute successful conversions of campaigns with a CTA to visit a physical location

## Places Architecture

The following graphic provides a high-level view of the Places architecture:

![](.gitbook/assets/places-arch.png)

