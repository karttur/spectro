---
layout: post
title:  xSpectre geo-sampling
categories: xspectre
excerpt: "Geo-sampling data with xSpectre v06"
tags:
  - campaign
  - sampling
  - geo-sampling
  - location
  - geographic
  - xspectre
image: ts-mdsl-rntwi_RNTWI_id_2001-2016_AS
date: '2021-07-14 11:27'
modified: '021-07-14  11:27'
comments: true
share: true

---

## xSpectre sampling

This post describes sampling and log operations with the with the [xSpectre app](https://stulturum.stulta1.xspectre.com) and  [xSpectre spectrometer v0.6](https://karttur.github.io/arduino/spectrolum/spectrolum-v0061/). The [xSpectre app](https://stulturum.stulta1.xspectre.com) is not a true app, but a web-page written in [Progressive web-apps](https://web.dev/progressive-web-apps/), but it appears and work like an ordinary app.

## Prerequisites

You must have a user and then defined a _campaign_ prior to do any actual sampling. For the example in this post you must have defined a spatial (geo-located) campaign. You must also have an xSpectre spectrometer with the [installed Arduino code](../xspectre-code-install-v06/).

## Supported web browsers

xSpectre's app requires a modern browser supporting the Bluetooth Generic Attribute Profile [GATT](https://www.bluetooth.com/bluetooth-resources/intro-to-bluetooth-gap-gatt/). We have not yet made a thorough testing of browser compatibility, instead we recommend that you use Chrome, either on a computer or a mobile device.  

## xSpectre app

The [xSpectre app](https://stulturum.stulta1.xspectre.com) is under fast development, the version covered here is for the generation v0.6 spectrometers.

 When you start the [xSpectre app](https://stulturum.stulta1.xspectre.com), the first page is the login.

 <figure>
 <img src="../../images/xspectre_app_v06_login.png">
 <figcaption> Login page for the xSpectre app version 0.6, </figcaption>
 </figure>

 The default welcome page after login shows sampling _campaigns_ associated with your user.

 <figure>
 <img src="../../images/xspectre_app_v06_welcome.png">
 <figcaption> Welcome page with campaigns associated with the logged in user for the xSpectre app version 0.6. </figcaption>
 </figure>

### Select _campaign_

Selecting a _campaign_, the properties of the chosen _campaign_ are displayed:

- Spectrometer (device) version
- A specific spectral sensor
- Geolocated (spatial) or not
- Temporal recording (time series) or not
- Variables to study
- Sampler extensions to use

<figure>
<img src="../../images/xspectre_app_v06_campaign.png">
<figcaption> Campaign page for the xSpectre app version 0.6. </figcaption>
</figure>

#### Spectrometer version

The version defines the hardware that builds the specific spectrometer used for the campaign as well as some of the default settings. This property can not be changed. if you get another generation of the spectrometer and want to continue an existing campaign you must start a completely new campaign.

#### Specific sensor

The different generation of sensors come with different spectral sensors. Like with versions, you can not change the the type of sensor used for a specific campaign. Version 0.6 of the spectrometer comes with three different sensor options:

- AMS 6-band visible (VIS) sensor
- AMS 6-band near infra red (NIR) sensor
- Hamamatsu 288 band visible (VIS) sensor

Note, however that the Hamamatsu VIS sensor reaching into the red edge and NIR bands, but a second type of Hamamatsu sensor covering a larger range of NIR wavelengths is under development.

#### Geolocated and/or temporal campaigns

Any campaign has two Boolean (yes/no) properties: _Spatial_ and _Time series_. For _Spatial_ campaigns all samples must have geographic point coordinate [We should give an area for which the sample is valid e.g. 1 m2)], and all samples in a campaign defined as a _time series_ must have a time stamp. A campaign can be both _Spatial_ and a _Time series_ at the same time.

#### Variables

When starting a campaign the variables to observe, apart from the spectra, must be defined with the campaign. At present this can not be changed or updated once the campaign has been defined. Variables does not need to be at ratio or interval scale, also ordinal data (like good - better - best) can be used. Nominal data can also be registered, but modeling of nominal classes is at present not supported.

#### Sampler extension

Version 0.6 of the xSpectre spectrometer comes with approximately a dozen [sampler attachments](https://karttur.github.io/arduino/spectrolum/spectrolum-v006-attachments/). All _campaigns_ are based on at least one sampler attachment. The sampling attachments differs regarding two properties: 1) the light source, and 2) the type of sample. The light source and the type of sensor go hand in hand; thus a project using a VIS sensor should also use a light source with emissions in the visible wavelength region. The type of samples at present include: i) direct, ii) solid, and iii) liquid.

### Add and define _Location_

Adding spectra and other data observations, click the <span class='button'>Locations</span> button and then <span class='button'>Add location</span> in the Location window:

<figure>
<img src="../../images/xspectre_app_v06_add-location.png">
<figcaption> Add location for a spatial campaign for the xSpectre app version 0.6. </figcaption>
</figure>

In the New location window, fill in the Location Name and any Comment:

<figure>
<img src="../../images/xspectre_app_v06_new-location.png">
<figcaption> Add location for a spatial campaign for the xSpectre app version 0.6. </figcaption>
</figure>

Click <span class='button'>Create Location</span> and you will come to the stage where you set the geographic (longitude / latitude) position. The xSpectre app v0.6 requires that you have a GPS connected to set the position. It might take a minute for the GPS to get a proper position. If the GPS signal is insufficient (dense canopy, buildings) you might need to alter the position slightly.

<figure>
<img src="../../images/xspectre_app_v06_position.png">
<figcaption> Position registered for spatial sampling campaign. </figcaption>
</figure>

### Add sample



## xSpectre log and tracking

The commands sent to and from the xSpectre app are build using the json protocol. Under the hood, the xSpectre app logs the processing. To access the logs and trace bugs and errors, the easiest is to use run the xSpectre app on a computer using Google´s web browser <span class='app'>Chrome</span>.

With the app open in a browser window, open the developer tools via <span class='app'>Chrome's</span> main menu:

<span class='menu'>View -> Developer -> Developer Tools</span>

<figure>
<img src="../../images/chrome-menu-developer-tools.png">
<figcaption>Open Developer Tools in Chrome web browser.</figcaption>
</figure>

### json prettifyer

Add a json prettifyer...
