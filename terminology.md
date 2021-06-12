---
description: Explanations of the terms used throughout this site and within MIDI Mixer.
---

# 💬 Terminology

## Profiles

A named collection of [**Groups** ](terminology.md#groups)and [**Controls** ](terminology.md#controls)that can be "loaded" against a given MIDI device, a [**Profile** ](terminology.md#profiles)is a map of the target device that MIDI Mixer can understand.

MIDI Mixer maintains some profiles as **Presets**, which are simply profiles that are shipped with the software and are intended to work out-of-the-box with the default configuration of the target device.

## Groups

A collection of [**Controls**](terminology.md#controls), a [**Group** ](terminology.md#groups)is assigned to a particular application, device, or plugin within MIDI Mixer and provides multiple [**Controls** ](terminology.md#controls)to perform different actions.

\*\*\*\*[**Groups** ](terminology.md#groups)are synonymous with "channels" on mixers; in the image below, "Channel 1", would be a [**Group** ](terminology.md#groups)within MIDI Mixer.

![A &quot;channel&quot; on a mixer is synonymous with a &quot;group&quot; in MIDI Mixer](.gitbook/assets/image%20%2811%29.png)

If we were using the above mixer and assigned our highlighted [**Group** ](terminology.md#groups)to the Discord application, we could now use any of the [**Controls** ](terminology.md#controls)within that group to perform different actions to that application, like changing volume, muting, or starting the application.

A [**Group** ](terminology.md#groups)can currently map the following [**Controls**](terminology.md#controls), with each one able to specify an [**Indicator** ](terminology.md#controls)too. You can add as many controls/indicators to each section as you like.

* **Volume** - _Faders only_ Controls and shows the volume of the group's assignment. This is usually faders or knobs as the controls, along with LED indicators or motorised faders for representing the current volume.
* **Peak meter** - _Indicators only_ Shows the current audio level being output by the assigned application or device.
* **Mute** - _Buttons only_ Controls and shows whether or not the group's assignment is muted. The provided indicator will be on if the assignment is muted, and off if it is not.
* **Assign** - _Buttons only_ If the group is currently unassigned, the indicator will be off and pressing the button will assign the group to whichever app is currently in focus. If the group is currently assigned, the indicator will be on and pressing the button will un-assign the group.
* **Run** - _Buttons only_ If the group is assigned to a device, the indicator represents whether or not the device is the default, and using the control will set the default device to the assignment. If the group is assigned to a session, the indicator represents whether or not the application is active, and using the control will either start or switch to the application.

Here's an example of the Behringer X-Touch Extender preset, defining controls for the first group.

![The &quot;Fader 1&quot; group of the Behringer X-Touch Extender preset](.gitbook/assets/image%20%286%29.png)

## Controls

A [**Control** ](terminology.md#controls)represents a single function of a mixer, separated in to **Faders**, **Buttons**, and **Indicators**.

A **Fader** defines an analog control and should be used for to define faders and rotaries.

![The &quot;Fader 1&quot; control of the Behringer X-Touch Extender preset](.gitbook/assets/image%20%288%29.png)

A **Button** defines any single-press control like, well, buttons or velocity-sensitive pads.

![The &quot;Rec 1&quot; button of the Behringer X-Touch Extender preset](.gitbook/assets/image%20%289%29.png)

An **Indicator** defines an LED, motorised fader, or some other feedback-related MIDI messages that will be sent _back_ to your MIDI device to display the current state of your system's audio.

![The &quot;Fader motor 1&quot; indicator of the Behringer X-Touch Extender preset](.gitbook/assets/image%20%2816%29.png)

## Buttons

Currently, the **Buttons** tab in the UI allows you to use any **Button** controls not in use by [**Groups** ](terminology.md#groups)and assign them generic actions unrelated to any particular application.

![Assigning the spare &quot;Media Record&quot; button to set the default output device of the system](.gitbook/assets/image%20%2815%29.png)

## Plugins

Plugins provide you with the ability to extend MIDI Mixer and leverage its core concepts to provide control for any application with generic rules that can apply to any MIDI device. Control apps, games, or even hardware like [Philips Hue lighting](https://github.com/midi-mixer/plugin-hue), helping other users get the most out of their device.

To get a more in-depth overview of plugins, head over to the [**Plugins Overview**](plugins/overview.md).

The **Plugins** tab shows you the plugins you have installed as well as those that are currently active. 

![The &quot;Plugins&quot; tab in the MIDI Mixer UI](.gitbook/assets/image%20%2814%29.png)

