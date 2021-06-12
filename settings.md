---
description: App-wide settings to customise your MIDI Mixer.
---

# ⚙ Settings

The **Settings** page within MIDI Mixer provides some options to affect the behaviour of the entire app, as well as some useful buttons to help both me and you move towards an even better app!

## General

![The &quot;General&quot; settings on the Settings page](.gitbook/assets/image%20%2820%29.png)

### Logarithmic volume curve

A logarithmic volume curve gives you more control over the lower end of volume setting by making smaller increments the smaller the volume. If you find your volumes are frequently set to low values, this will greatly benefit.

![A logarithmic volume curve compared to a non-logarithmic \(linear\) volume curve](.gitbook/assets/image%20%2827%29.png)

As well as toggling the logarithmic curve on and off, you can also adjust the "steepness" of the curve using the slider provided. A higher number means a steeper curve.

### Start on boot

When enabled, MIDI Mixer will automatically start when your machine is booted up.

### Start minimised

When enabled, MIDI Mixer will not open the main UI when it's started, and will instead load directly in to the task tray.

![MIDI Mixer in the task tray](.gitbook/assets/image%20%2819%29.png)

### Analytics & Crash Reports

When enabled, this option helps improve MIDI Mixer by automatically sending diagnostics, crash reports, and usage data whenever an error occurs. All data is collected entirely anonymously and contains no personal information whatsoever, but you can disable it if you wish.

## OSD

The MIDI Mixer On-Screen Display \(OSD\) is an extra windows that will appear above most windows to show you what you're controlling at that current moment in time.

![An example OSD showing the current volume of the Spotify application](.gitbook/assets/image%20%2828%29.png)

### Enabled

Toggle whether or not the OSD will ever be shown using this.

### Position

The position for the OSD to be displayed on the screen selected. Can either be "Top left", "Top right", "Bottom left", or "Bottom right".

### Screen

The screen to show the OSD on. The OSD currently has no DirectX hook so can't be shown above full-screen applications like games. If you have multiple screens, placing it not on the primary screen is often a good idea.

## Compatibility

### MIDI Passthru

MIDI devices can only be used by one application at a time. This means that if you're using your MIDI device with MIDI Mixer then other applications can't use it. There are legitimate reasons for wanting to use your device with multiple applications at the same time, and MIDI Passthru helps you to do that.

![Selecting the &quot;X-TOUCH MINI&quot; device](.gitbook/assets/image%20%2821%29.png)

When a [**Profile** ](terminology.md#profiles)is loaded against a particular device and a "MIDI Passthru" is selected, a copy of the input will also be sent to whatever is selected in this option. This is a very powerful tool to use with an application like [loopMIDI](https://www.tobias-erichsen.de/software/loopmidi.html), giving you access to multiple virtual MIDI devices from one actual device.

For example, I have an **X-TOUCH MINI** device that I'm using with MIDI Mixer. I start **loopMIDI** and select **loopMIDI Port 1** as the "MIDI Passthru".

Now, whenever I hit a button on my **X-TOUCH MINI**, that button press is also sent to the virtual **loopMIDI Port 1** device. To use the passthru with another application, I just have to use the **loopMIDI Port 1** device in the other application and you're set!

## Updates

The updates section within the settings page gives you control over when and how MIDI Mixer updates itself.

{% hint style="success" %}
\*\*\*\*[**Contributors** ](accounts/contribution.md)have access to the [**Alpha** ](accounts/contribution.md#what-do-i-get)release channel, providing access to features and builds before other users.
{% endhint %}

![The MIDI Mixer updates section of the Settings page](.gitbook/assets/image%20%2824%29.png)

### Check for updates

Clicking this button will check the selected release channel \(Stable or [Alpha](accounts/contribution.md)\) for the latest build available.

If an update is found and you have automatic updates enabled, MIDI Mixer will immediately start downloading and installing the update. If you don't, you'll be given an option to download the update and another to install it once the download is complete.

### Keep up to date automatically

If enabled, MIDI Mixer will automatically download and install updates when your system is idle.

{% hint style="info" %}
Internally, MIDI Mixer will only ever automatically check for updates when the app starts so as to be as unintrusive as possible.
{% endhint %}

**Leaving this option enabled is highly recommended as it not only ensures you're getting access to the latest features, but also the latest bug fixes and security updates.**

### **Release channel**

You can change your release channel between two values: **Stable** and [**Alpha**](accounts/contribution.md).

Only [**Contributors**](accounts/contribution.md) have access to the **Alpha** channel, providing access to features and builds before other users.

Once selected, if you have automatic updates enabled, MIDI Mixer will automatically up- or down-grade to the latest update for that given release channel. If you don't you'll be given an option to download the update and another to install it once the download is complete.

