# ASIL_HybridEngine
Hybrid Engine (Headphone &amp; speakers) for artists who want to explore interactive 3D soundfields in ASIL Labs
<p align="center"> 
<img src="/images/Concept.jpg" height="400" />
</p> 

## ASIL_HybridEngine: binaural headphone rendering of direct path & early reflections
<p align="center"> 
<img src="/images/animation-headphones.gif" width = "350">
</p> 

## ASIL_HybridEngine: 7th order ambisonics reverb rendering in ASIL speakers
<p align="center"> 
<img src="/images/animation-reverb.gif" width = "350">
</p> 


## Requirements
- Ableton Live 11 suite with embedded Max MSP
- Enevelop4live v11 - [Download](https://github.com/EnvelopSound/EnvelopForLive/releases/tag/11.0.1)
- IEM Plugin Suite v1.14 - [Download](https://plugins.iem.at/download/)
- Experience in Ableton Live

## Installation
* [Download](https://plugins.iem.at/download/) and install the latest version of IEM plugin Suite
  * From Ableton, open any Max4Live Patch in the max editor and add the VST install directory to the max path (options -> File Preferences -> add...)
* [Download](https://github.com/EnvelopSound/EnvelopForLive/releases/tag/11.0.1) the latest release of Envelop4Live 
  - Unzip the file and place the **Envelop for Live** folder in a good location on your hard drive
  - For easy access, you may wish to bookmark the **Envelop for Live** folder in the Places section of Ableton Live. Do this by dragging and dropping the folder, or using the "Add Folder..." button.
  - <img src="https://github.com/EnvelopSound/EnvelopForLive/raw/master/doc/E4L-Places-Add.png"/>
* Download patches in this repo the the same direcotry

## Getting started with IEM Plugin Suite
* Please refer to the IEM site for a quick [walkthrough](https://plugins.iem.at/docs/)
* Master at least the plugins:
  * [SceneRotator](https://plugins.iem.at/docs/plugindescriptions/#scenerotator)
  * [FdnReverb](https://plugins.iem.at/docs/plugindescriptions/#fdnreverb)
  * [RoomEncoder](https://plugins.iem.at/docs/plugindescriptions/#roomencoder)
  
## Getting Started with Envelop4Live
- Make sure to master [Envelop4live](https://github.com/EnvelopSound/EnvelopForLive/wiki)
  - [Getting Started](https://github.com/EnvelopSound/EnvelopForLive/wiki/Getting-Started) - quick guide to basic installation and usage
  - [Routing Architecture](https://github.com/EnvelopSound/EnvelopForLive/wiki/Routing-Architecture) - understand the E4L routing architecture
  - [System Overview](https://github.com/EnvelopSound/EnvelopForLive/wiki/System-Overview) - a high-level view of the tools and technology

- Master at least the following devices in Envelop4live:
  - [E4L Master Bus](https://github.com/EnvelopSound/EnvelopForLive/wiki/E4L-Master-Bus) 
  - [E4L Source Panner](https://github.com/EnvelopSound/EnvelopForLive/wiki/E4L-Source-Panner)
  - [E4L Mono Panner](https://github.com/EnvelopSound/EnvelopForLive/wiki/E4L-Mono-Panner)
  - [E4L Multi-Delay](https://github.com/EnvelopSound/EnvelopForLive/wiki/E4L-Multi-Delay)


## Preparing ASIL for use with Hybrid Engine
On the IPEM PC's, all patches & presets can be found in **Z:\__ SOFTWARE\Ambisonics\Envelop4Live-Hybrid\**
- Get the wireless transmittors (in the rack drawer), configure as needed & connect to the headphones 
- On the Audio Rack PC, load the dante preset **"Z:\__ SOFTWARE\Ambisonics\Envelop4Live-Hybrid\Dante\DANTE_Ambisonics_RACKPC-hybridEngine.xml"**
- On the Mocap PC, use the "Mocap_ASIL_HeadphoneTracking_Hybrid" project.  Calibrate & configure P1 & P2 rigid bodies.

## Getting Started with the Hybrid Engine
- Place the "IPEM_Hybrid_MasterBus.amxd" on the first (audio) track; configure as needed (see workshop)
  - <img src="/images/Masterbus.jpg">
  - From left to right, you have the following components:
    - Input for visualisation of input signal
    - Listener configuration: P1 & P2 input can be mocap or OSC input or random input
    - Input alignment: each participant should go the center of ASIL & watch forward to the radio side. At that moment they can be calibrated ("set zero")
    - Room configuration: includes width, height, depth, reflections & attenuation
    - Scene overview for graphical represention of the room & listeners  
    - Gain control: the balance between headphone & speakers
    - Output: 64 channel output for ASIL.  The 4 dB meters below can be used for master volume.
- Place the "IPEM_Hybrid_Source.amxd" on each track with a sound source; configure as needed (see workshop)
  - <img src="/images/source_2.jpg">
  - Includes input selection options (mouse, circle, mocap, osc, ...)

