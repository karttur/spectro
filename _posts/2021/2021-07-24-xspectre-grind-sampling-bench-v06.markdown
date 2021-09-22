---
layout: post
title:  xSpectre bench analysis
categories: xspectre
excerpt: "Spectral analysis using bench-top spectrometer"
tags:
  - campaign
  - grind
  - sampling
  - bench-top
  - benchmark
  - xspectre
image: ts-mdsl-rntwi_RNTWI_id_2001-2016_AS
date: '2021-07-24 11:27'
modified: '021-07-24  11:27'
comments: true
share: true
---

## xSpectre bench-top spectrometer analysis

This post describes how to combine xSpectre's sampling equipment with any external bench-top spectrometer that can be connected using fibre optic cables and SMA905 connectors. The example here is for a soil sample, using a grind (solid) snout. The example covers two different lamps, an [OSRAM's Oslon NIR-LED](#) and a [Barthelme xenon bulb](#).

## Prerequisites

Apart from an xSpectre spectrometer including external snouts with [SMA905 connectors](arduino/optics-SMA905/), you also need a bench-top spectrometer with an SMA905 connection.

## Applications

To use a bench-top spectrometer together with the xSpectre fibre optic snout you need to run the xSpectre and spectrometer apps in parallel. For this post I have used [Spectrometry](https://www.pasco.com/downloads/spectrometry) from [Pasco](https://www.pasco.com) together with an Amadeus educational spectrometer (no longer in production, but [video presentation available on youtube](https://www.youtube.com/watch?v=st0N8ME2PSI)). The equivalent spectrometer available at time of writing this in July 2021 is the [PS-2600 wireless spectrometer](https://www.pasco.com/products/sensors/wireless/ps-2600), also available in Sweden from [Sagitta](https://www.sagitta.se/artikel/spektrometer-tradlos#.YQEWzC0RrOQ)

![xspectre-welcome-campaign-admin](../../images/xspectre-welcome-campaign-admin.png)
{: .pull-right}
### xSpectre app

Start the xSpectre app on you computer (use <span class='app'>chrome</span>) and after the usual login, select the _Admin_ options from the _Choose campaign_ list on the _Welcome_ page (see figure).

![xspectre-connect-admin](../../images/xspectre-connect-admin.png)
{: .pull-left}

&nbsp;
&nbsp;

Connect to your xSpectre spectrometer and then pair the spectrometer using bluetooth.

<figure>
	<img src="../../images/xspectre-pair-admin.png" alt="image">
</figure>

![xspectre-lamp-on-off-admin](../../images/xspectre-lamp-on-off-admin.png)
{: .pull-right}

The app presents three options:

- Disconnect
- Lamp on
- Lamp off

&nbsp;
&nbsp;

Just click _Lamp on_ to turn the TRX connected snout lamp on and _Lamp off_ to turn it off.

<figure class="half">
	<img src="../../images/xspectre-lamp-off-osram-nir.png" alt="image">
  <img src="../../images/xspectre-lamp-on-osram-nir.png" alt="image">
	<figcaption>Turn on/off the xSpectre snout lamp.</figcaption>
</figure>

Connect the fibre optic cable to the bench-top spectrometer.

<figure>
	<img src="../../images/xspectre-sample-setup-grind-osram-nir-admin.png" alt="image">
	<figcaption>Sampling setup using xSpectre snout lamp and a bench-top spectrometer.</figcaption>
</figure>

### Spectrometry app

Start the <span class='app'>Spectrometry</span> app.

<figure>
	<img src="../../images/Pasco-spectrometry_start-page.png" alt="image">
	<figcaption>Start page of Pasco´s Spectrometry app.</figcaption>
</figure>

![Pasco-spectrometry_analyze-light-button](../../images/Pasco-spectrometry_analyze-light-button.png)
{: .pull-right}
As this example is for a grind (solid) sample (soil), select the _Analyze Light_ option in the top row of <span class='app'>Spectrometry</span>.

![Pasco-spectrometry_analyze-light-button](../../images/xspectre-sample-setup-grind-admin.png)
{: .pull-left}
Turn on the snout lamp from the <span class='app'>xSpectre</span> app. Set the snout properly over the grind sample holder with soil.

![Pasco-spectrometry_record-button-round](../../images/Pasco-spectrometry_record-button-round.png)
{: .pull-right}
Then click on the _Record_ button in the <span class='app'>Spectrometry</span> app. The button turns into a square and the spectrometers records the signal received through the fibre optic cable.

&nbsp;

![Pasco-spectrometry_tool-menu](../../images/Pasco-spectrometry_tool-menu.png)
{: .pull-left}
The tools in the <span class='app'>Spectrometry</span> tool menu (to the left) will light up and become available. Click the option _Auto set_ under _Integration Time_ and wait for the _Determining best integration time_ to finish. Set the _Number of scans to average_ to 6. Leave _Smoothing_ set to 0.

&nbsp;

![Pasco-spectrometry_scale-to-fit-btn](../../images/Pasco-spectrometry_scale-to-fit-btn.png)
{: .pull-right}
Click the _Scale to Fit_ icon in the lower menu bar to adjust the main view to fit the spectra.

&nbsp;

You should now see the spectral response of your sample in the main view of <span class='app'>Spectrometry</span>.

<figure>
	<img src="../../images/Pasco_20210728_goransdal-01-h_grind_osram-nir.png" alt="image">
	<figcaption>Spectral recording in Pasco's Spectrometry app.</figcaption>
</figure>


![Pasco-spectrometry_source1-label](../../images/Pasco-spectrometry_source1-label.png)
{: .pull-right}
Make sure the snout lamp is on and then rename this first sample by clicking the _Source #x_ label above the spectral graph. The label should indicate both the lamp (or dark) and the sample reference.

![Pasco-spectrometry_record-button-round](../../images/Pasco-spectrometry_record-button-round.png)
{: .pull-right}
Then again click the, now square _Record_ button in the <span class='app'>Spectrometry</span> app. The button turns round again and the sample is saved.

&nbsp;

Repeat the sampling procedure with the snout lamp turned off. Label the sample with the light source given as _dark_. You do not need to create a new _dark_ with each sample; you can use a global _dark_ for your bench-top spectrometer, or, preferably, create a dark reference for each session. Similarly you can create a reflectance reference, preferably using a certified reflectance standard, or a standard white surface. It is actually more important to calibrate the white reference as this changes with both the lamp, and the ambient light and temperature.

Save the session ...

![Pasco-spectrometry_snapshot](../../images/Pasco-spectrometry_share.png)
{: .pull-right}
Export the recorded as a <span class='file'>.csv</span> spectra by clicking the _Share_ button and then _Export Data_ (the only option).

![Pasco-spectrometry_snapshot](../../images/Pasco-spectrometry_snapshot.png)
{: .pull-right}
You should now have 1, 2 or 3 recorded samples. You can take snapshots of each sample by clicking the respective label in the <span class='app'>Spectrometry</span> main view and then click the _Take journal snapshot_ in the top menu. The two sets of figures below shows the spectra using two different lamps (electomagnetic emitters); the top images show the spectra from a NIR LED (OSRAM OSLON) and the lower images show the spectra from a xenon light bulb.

<figure class="third">
	<a href="../../images/Pasco_20210728_grind_dark.png"><img src="../../images/Pasco_20210728_grind_dark.png" alt="image"></a>
  <a href="../../images/Pasco_20210728_goransdal-01-h_grind_osram-nir.png"><img src="../../images/Pasco_20210728_goransdal-01-h_grind_osram-nir.png" alt="image"></a>
  <a href="../../images/Pasco_20210728_grind_reflectance-standard.png"><img src="../../images/Pasco_20210728_grind_reflectance-standard.png" alt="image"></a>
  <figcaption>Reflectance spectra using an LED NIR emitter source; left: dark, center: soil sample, right: white (ceritified) reflectance standard. All spectra are smoothed using 12 consecutive recordings. Click on one of the images for larger views.</figcaption>
</figure>

<figure class="third">
	<a href="../../images/Pasco_20210728_grind_xenon_dark.png"><img src="../../images/Pasco_20210728_grind_xenon_dark.png" alt="image"></a>
  <a href="../../images/Pasco_20210728_grind_xenon_goransdal01-h.png"><img src="../../images/Pasco_20210728_grind_xenon_goransdal01-h.png" alt="image"></a>
  <a href="../../images/Pasco_20210728_grind_xenon_reflectance-standard.png"><img src="../../images/Pasco_20210728_grind_xenon_reflectance-standard.png" alt="image"></a>
  <figcaption>Reflectance spectra using a xenon emitter source; left: dark, center: soil sample, right: white (ceritified) reflectance standard. All spectra are smoothed using 12 consecutive recordings. Click on one of the images for larger views.</figcaption>
</figure>
