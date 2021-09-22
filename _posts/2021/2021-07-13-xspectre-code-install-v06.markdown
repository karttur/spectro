---
layout: post
title:  Install xspectre code
categories: xspectre
excerpt: "Install xspectre arduono code v0.6"
tags:
  - arduino
  - code
  - xspectre
image: ts-mdsl-rntwi_RNTWI_id_2001-2016_AS
date: '2021-07-13 11:27'
modified: '2021-07-13  11:27'
comments: true
share: true

---

## xSpectre spectrometer code

The [xSpectre spectrometer v0.6](https://karttur.github.io/arduino/spectrolum/spectrolum-v0061/) is run on [Arduino IDE](https://www.arduino.cc/en/software) internal code and an [Arduino33 IoT](https://karttur.github.io/arduino/module/module-nano-iot-33/). This post covers how to clone the most recent version of the Arduino code and install it on the micro-controller.

## Prerequisites

You have to have login rights to the [Bitbucket](https://bitbucket.org) repository at [https://bitbucket.org/xspectre/arduino](https://bitbucket.org/xspectre/arduino). You must also have installed the [Arduino Integrated Development Environment (IDE)](https://www.arduino.cc/en/software). Dependent on your operating system you might also need to install specific drivers to actually connect your Arduino micro controller (board) to a usb-pot on your machine.

## Cloning repo

If you have not previously cloned xspectre's repository for Arduino [https://bitbucket.org/xspectre/arduino/src/master](https://bitbucket.org/xspectre/arduino/src/master/]) you need to make an initial clone. If you already have a clone, you only need to _pull_ any recent changes, and thus skip over the next section.

### Initial cloning

Open a browser and navigate to

```
https://bitbucket.org/xspectre/arduino/src/master/
```

<figure>
<img src="../../images/bitbucket_arduino_master.png">
<figcaption> Master branch of the xspectre/arduino repo at Bitbucket.com.</figcaption>
</figure>

Click on the <span class='button'>Clone</span> button and then select the cloning method (the default method HTTPS is fine). Copy the _git clone_ command.

<figure>
<img src="../../images/bitbucket_arduino_master_clone.png">
<figcaption>Select cloning method (HTTPS is fine).</figcaption>
</figure>

### Clone with terminal

Start a <span class='app'>Terminal</span> session and change directory <span class='terminalapp'>cd</span> to the parent directory where you want to store the local clone of the xspectre/arduino repo. Then just paste the copied code to the command line:

<span class='terminal'>$ git clone https://user@bitbucket.org/xspectre/arduino.git</span>

<span class='temrinalapp'>cd</span> into the local clone:

<span class='terminal'>$ cd arduino</span>

List <span class='terminalapp'>ls</span> the content of the local clone:

```
$ ls
libraries	mojjang
```

The clone contains different files and folders used for the code development; the folders containing the code required for compiling and uploading to the spectrometer are under the directories _libraries_ and _mojjang_.


### Pull updates

If you already have a local clone of the xspectre/arduino repo, open a <span class='app'>Terminal</span> window and change directory <span class='terminalapp'>cd</span> to the clone top directory. Then just run the command:

<span class='terminal'>$ git pull</span>

## Start Arduino

The main Arduino code (<span class='file'>.ino</span>) file is <span class='file'>mojjang/mojjang.ino</span>. To start <span class='app'>Arduino IDE</span> with this file, you can either use the terminal

<span class='terminal'>$ cd mojjang<br/>$ open mojjang</span>

of start the <span class='app'>Arduino IDE</span> app and open the <span class='file'>mojjang.ino</span> from the menu:

<span class='menu'>File -> Open</span>

### Compile

The latest version of xSpectre´s spectrometer code should now be loaded into <span class='app'>Arduino IDE</span>:

<figure>
<img src="../../images/mojjang_ino_v06.png">
<figcaption>mojjang.ino version 0.6, includes and declarations.</figcaption>
</figure>

![compile_btn](../../images/arduino_compile_btn.png)
{: .pull-right}
Try to compile the code using the check key (right). If the code does not compile and protests that a specific library is missing, you have to copy the library content from the cloned repo to the default path for Arduino defined when you installed the Arduino IDE.

### Upload

![upload_btn](../../images/arduino_upload_btn.png)
{: .pull-right}
Once you have compiled the <span class='file'>.ino</span> code file, upload it to the micro-controller by clicking the upload button (right).
