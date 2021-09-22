---
layout: post
title:  Landsat bands
categories: spectr
excerpt: "Landat bands for handheld sensor"
tags:
  - article
  - visible
  - wood
image: ts-mdsl-rntwi_RNTWI_id_2001-2016_AS
date: '2021-06-29 11:27'
modified: '2021-06-29 11:27'
comments: true
share: true

---

[Landsat](https://www.usgs.gov/faqs/what-are-band-designations-landsat-satellites?qt-news_science_products=0#qt-news_science_products) and [Sentinel](https://www.satimagingcorp.com/satellite-sensors/other-satellite-sensors/sentinel-2a/) bands:

| sensor | band | Wavelength |
| Landsat | Band 1 - Coastal aerosol | 0.43-0.45 |
| Landsat | Band 2 - Blue | 0.45-0.51 |
| Landsat | Band 3 - Green | 0.53-0.59 |
| Landsat | Band 4 - Red | 0.64-0.67 |
| Landsat | Band 5 - Near Infrared (NIR) | 0.85-0.88 |
| Landsat | Band 6 - SWIR 1 | 1.57-1.65 |
| Landsat | Band 7 - SWIR 2 | 2.11-2.29 |
|   |   |   |
| Sentinel | Band 1 - Coastal aerosol | 0.443 |
| Sentinel | Band 2 - Blue | 0.490 |
| Sentinel | Band 2 - Blue | 0.490 |
| Sentinel | Band 3 - Green | 0.560 |
| Sentinel | Band 4 - Red | 0.665 |
| Sentinel | Band 5 - Red Edge | 0.705 |
| Sentinel | Band 6 - Red Edge | 0.740 |
| Sentinel | Band 7 - Red Edge | 0.783 |
| Sentinel | Band 8 - Near Infrared (NIR)  | 0.842 |
| Sentinel | Band 8A - Red Edge | 0.865 |
| Sentinel | Band 9 - Water vapour | 0.945 |
| Sentinel | Band 10 - SWIR cirrus | 1.375 |
| Sentinel | Band 11 - SWIR 1 | 1.610 |
| Sentinel | Band 12 - SWIR 2 | 2.190 |

[Pyreos PY2572 1-4 channel analog sensors](https://pyreos.com/ir-to-39-detectors/?productnum=PY2572) do not cover this range.

[Hamamatsu IR sensors]()

P10090-01 (non-cooled) https://www.hamamatsu.com/resources/pdf/ssd/p10090-01_etc_kird1099e.pdf

### Light resources

For the VIS-NIR region, standard lamps (white LED, xenon, OSRAM NIR) are OK. The problem is to identify suitable lamps and sensor for the region 1300 to 2400 nm.

I[HeimannSensor](https://www.heimannsensor.com) offers the low cost and robust [HSL series](https://www.heimannsensor.com/HSL-Series) that should be possible to build directly into an microcontroller using a [MOSFET](#). But it is doubtful whether it comes down all the way to 1300 nm.

[IBSG](http://www.ibsg-st-petersburg.com) (Russia) offers IR LED emitters with fixed wavelengths from 0.7 to 5.0 um. Covering the Landsat/Sentinel spectral bands, the following alternatives are available:

- [LED15HP (1.53 um, +/-90nm)](http://www.ibsg-st-petersburg.com/led_1HP.html)
- [LED17HP (1.74 um, +/-150nm)](http://www.ibsg-st-petersburg.com/led_1HP.html)
- [LED21 (2.15 um, +/-150 nm)](http://www.ibsg-st-petersburg.com/led_1.html)

Hamamatsu has a lamp at 1.55 um with a half-width of 120 nm, [L12509-0155P](https://www.hamamatsu.com/eu/en/product/light-and-radiation-sources/led/index.html)

### Sensors (Photodiods)

[IBSG Photodiodes for 0.8-2.4 µm spectral range](http://www.ibsg-st-petersburg.com/phd_2.html)
