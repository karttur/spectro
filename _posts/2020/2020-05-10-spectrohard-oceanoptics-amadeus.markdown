---
layout: post
title: Ocean optics Amadeus
categories: spectrohard
excerpt: "Ocean Optics Amadeus spectrometer for education"
tags:
  - spectrometer
  - Ocean optics
  - Amadeus
image: ts-mdsl-rntwi_RNTWI_id_2001-2016_AS
date: '2020-05-29 11:27'
modified: '2020-05-29 T18:17:25.000Z'
comments: true
share: true
figure1: machinelarning_histo_housing
figure3A: machinelarning_linregnaive
figure3B: machinelarning_linregmodel
---

## Introduktion

Back in 2013 I got myself an Ocean Optics Amadeus spectrometer for educational purposes. The Amadeus is a fairly simple grating spectrometer. I got mine from
[gammadata](https://www.gammadata.se) in Sweden, but they no longer sell educational equipment. And the Amadeus version I got is no longer produced (I think). It, however, came with a handy optical cable and a light source.

On youtube, there is [The Amadeus Spectrometer](https://www.youtube.com/watch?v=vswZsBAR6gc) instruction video by [Pasco scientific](https://www.pasco.com).

## Software

The [Pasco free spectrometer software](https://www.pasco.com/downloads/spectrometry), available for Mac OSX and Windows. Pasco's own [instruction video](https://www.pasco.com/resources/video/i5BexMng2WY). I just plugged in the Ocean Optics Amadeus usb, and it connected to the free spectrometer software. https://www.youtube.com/watch?v=i5BexMng2WY

If you want a bit more advanced software, instead try  [SPARKvue](https://www.pasco.com/products/software/sparkvue#download-panel), also by PASCO. It has 60 days free use.

[Ocean Optics]() also have a commercial software that is advertised to run for all their spectrometers: [spectrecology](https://www.spectrecology.com/software-ocean-optics-spectrometers/)  - Spectroscopy & Optical Sensing Solutions. It has 10 day free trial. Amadeus is not in the list of supported spectrometer, even if it is from Ocean Optics.

### Python alternative

There is a Python library that can be used to access Ocean Optics spectrometers called [Seabreeze](https://pypi.org/project/seabreeze/). Then you can go on and build a complete analysis tool from [pyUVVIS](http://ddietze.github.io/pyUVVIS/index.html).
