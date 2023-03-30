# ASIL_HybridEngine
Hybrid Engine (Headphone &amp; speakers) for artists who want to explore interactive 3D soundfields in ASIL Labs

## Requirements
- Ableton Live 11 suite with embedded Max MSP
- Enevelop4live v11 - Download links https://github.com/EnvelopSound/EnvelopForLive/releases/tag/11.0.1

## Installation
* Download the latest release of Envelop4Live (https://github.com/EnvelopSound/EnvelopForLive/releases/download/11.0.0/Envelop.for.Live.11.0.0.zip)
* Unzip the file and place the **Envelop for Live** folder in a good location on your hard drive
* For easy access, you may wish to bookmark the **Envelop for Live** folder in the Places section of Ableton Live. Do this by dragging and dropping the folder, or using the "Add Folder..." button.
![Places](https://github.com/EnvelopSound/EnvelopForLive/raw/master/doc/E4L-Places-Add.png)
- Download patches in this repo the the same direcotry

## Getting Started with Envelop4Live
- Make sure to master Envelop4live: see https://github.com/EnvelopSound/EnvelopForLive/wiki
E4L makes use of the advanced routing capabilities in Live 11+ and Max for Live. Before continuing, make sure that you have installed both of these packages.

Getting Started (https://github.com/EnvelopSound/EnvelopForLive/wiki/Getting-Started) - quick guide to basic installation and usage
Routing Architecture (https://github.com/EnvelopSound/EnvelopForLive/wiki/Routing-Architecture) - understand the E4L routing architecture
System Overview (https://github.com/EnvelopSound/EnvelopForLive/wiki/System-Overview) - a high-level view of the tools and technology

- Master at least the following devices in Envelop4live:
E4L Master Bus (https://github.com/EnvelopSound/EnvelopForLive/wiki/E4L-Master-Bus) 
E4L Source Panner (https://github.com/EnvelopSound/EnvelopForLive/wiki/E4L-Source-Panner)
E4L Mono Panner (https://github.com/EnvelopSound/EnvelopForLive/wiki/E4L-Mono-Panner)
E4L Multi-Delay (https://github.com/EnvelopSound/EnvelopForLive/wiki/E4L-Multi-Delay)

### Create the E4L Master Bus

Create a new audio track. Add one of the **E4L Master Bus** device to this track. Note that the track will automatically be renamed to "E4L Master." It is recommended to leave this track name in place, though you may optionally rename it. This track and device will act as a receiver for Ambisonics audio, and allow you to monitor the output of a decoder.

<img src="https://github.com/EnvelopSound/EnvelopForLive/raw/master/doc/E4L-Master-Bus.png" alt="E4L Master Bus" height="188" />

By default, the **E4L Master Bus** device will use a **Binaural** decoder, which enables you to preview your spatial mix on a pair of headphones. Make sure that the **Monitor 1+2** switch is engaged. Input meters on the **E4L Master Bus** device provide a visual reference for whether the device is receiving input.

### Add Source Tracks

Now, create a new audio or instrument track. In the track's effect chain, add the **E4L Source Panner** device. This device takes a stereo input and encodes it into 16 channels of high order ambisonics. This device automatically detects the master bus and uses Max for Live's routing capabilities to send its output to the E4L Master Bus.

<img src="https://github.com/EnvelopSound/EnvelopForLive/raw/master/doc/E4L-Source-Panner.png" alt="E4L Source Panner" height="188" />

Note that by default, adding this device automatically sets the track's audio output routing to _Sends Only_. This is because E4L is already routing the Ambisonics-domain audio behind the scenes. Sending the stereo output from this track would result in two overlapping copies of the audio. For advanced use cases, you may override this setting and route the track output elsewhere (keep in mind that the track output sends only the stereo signal, not the 16-channel surround encoding).

Repeat this process to build up your surround mix. You may use as many **E4L Source Panner** devices as you like, on as many tracks as your CPU can handle.
