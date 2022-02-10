---
description: Frequently Asked Questions and common issues.
---

# ❓ FAQ

## My device isn't working

### Common steps

Make sure that **only** MIDI Mixer is using your device. If you have another program open that can use or make changes to your device, try closing it.

Another easy solution could be unplugging and replugging your device from your computer. Or maybe it's possible to reset your specific device to factory settings.

[Try and uninstall your device drivers and then re-install them.](faq.md#how-do-i-uninstall-and-re-install-drivers)

If that doesn't work, then check if your device needs specific drivers to function. You can usually find those on the official website for your device. If you already have those specific drivers, then also try and uninstall and then re-install them.

Even a computer restart could be the simple fix that's needed. And in rare cases, trying another computer port or another cable might fix the issue.

If all fails, let us know in on the [Discord server](https://discord.midi-mixer.com) in `#support`, and we'll try to help you get it working.

It's most helpful if you start by telling us the steps you've already tried to resolve the issue, and which device you have.

**If you don't tell us what you've tried or which device you have, we might assume that you haven't checked the FAQ yet and ask you to look at that first.**

### **Uninstalling and reinstalling drivers**

1. Right-click the Windows icon in the bottom left of your screen.
2. Select Device Manager.
3. Select Sounds, video & game controllers.
4. Right-click on your device's name.
5. Select Properties.
6. Go to the Driver tab.
7. Select Uninstall Device.
8. Re-install the drivers.

### My device sometimes disconnects

MIDI devices are usually used with [DAWs](https://en.wikipedia.org/wiki/Digital\_audio\_workstation) for relatively short periods of time, but there are frequent reports of these devices silently disconnecting, requiring a user to un-plug and re-plug the device in order to get it to work again.

If you're suffering from this problem, there are a few common steps that may help resolve your issue.

#### 1. Turn off USB selective suspend

The "USB selective suspend" option allows a USB hub driver to suspend an individual port without affecting the operation of other ports on the hub. It's usually used to save on power usage, but MIDI devices can often be mistaken for being inactive and therefore be turned off without warning.

To disable this:

![Go to "Edit power plan" settings](<.gitbook/assets/image (34) (1).png>) ![Select "Change advanced power settings"](<.gitbook/assets/image (33) (1) (1).png>) ![Set "USB selective suspend setting" to "Disabled", Apply, and exit](<.gitbook/assets/image (35) (1).png>)

#### 2. Connect directly to your PC

Hubs can interrupt certain USB power-saving settings and do their own thing, often causing unexpected behaviour in devices that maintain an open connection such as MIDI devices.

Connecting the device directly to your machine removes this potential problem, making sure we only have to worry about one cable and one port.

{% hint style="info" %}
A hub's overall speed is often automatically downgraded to the speed of the lowest performing device connected to it. For instance, if you plug a USB 1 device into it, all other devices on the hub are downgraded to USB 1 speed, which can cause issues.
{% endhint %}

#### 3. Replace the USB cable

Some users have found that using a different USB cable has solved their problem. To quote Ableton:

> \[...] use a short, high quality USB cable with a ferrite bead. Just one faulty or underperforming cable can sometimes knock out USB connection for all other USB devices currently connected to the computer.

#### 4. Try different ports

Depending on how your ports are connected to your motherboard, some ports might work differently than others, or might use differing USB versions. It's common for MIDI devices to not support USB, so try a few different ports on your machine to see if this helps.

#### 5. Turn off power saving for USB ports

Similar to the "USB selective suspend" option, Windows can forcibly shut down power to USB ports if it deems it necessary. In the case of MIDI devices that need to powered at all times, this can cause problems.

To disable this:

![Go to "Device Manager"](<.gitbook/assets/image (32) (1).png>) ![Expand "Universal Serial Bus controllers" and double-click all "USB Root Hub" devices](<.gitbook/assets/image (30) (1).png>) ![For each one, UNTICK "Allow the computer to turn off this device to save power", and click "OK"](<.gitbook/assets/image (31) (1) (1).png>)

#### 6. Make sure drivers and firmware are up to date

Whatever device you have, make sure you have the latest drivers from the manufacturer's website. You may have documentation from the manufacturer when you bought the device that tells you where to get drivers from, but make sure you have the latest versions available to ensure stable use of the device.

### **Behringer X-Touch Mini**

#### Make sure it is in MC Mode!

1. Unplug the cable from the XTM and locate the **MC button** in the lower left of the panel.
2. Keep that button pressed while you plug the cable back in and the XTM turns on.

All the buttons will flash twice and you'll know that it's in MC mode from the small light that will appear in the top right of the panel, right above the text, **MC MODE**.

### **Korg nanoKONTROL2**

If it's the lights that aren't working, then look [here instead](faq.md#how-do-i-get-the-lights-working-on-the-korg-nanokontrol-2).

First things first - Make sure you don't have other programs using your device, while you're trying to use MIDI Mixer with it.&#x20;

If you have the Korg Editor open, MIDI Mixer will not work.

#### Try resetting it!

1\. Unplug the device.

2\. Hold down the PREV. and NEXT buttons **and** the CYCLE button, and plug the cable back into the device, while holding the 3 buttons down.

3\. Once you see the bottom lights flashing, you can let go of the buttons. Your device has now been reset!

A visual guide can also be found in [this YouTube video](https://youtu.be/zCvaq0J-xuU?t=23).

#### Resetting didn't work?&#x20;

[Try uninstalling and re-installing the drivers](faq.md#how-do-i-uninstall-and-re-install-drivers).

#### Still no luck? Try using the Korg Driver Uninstaller

It's part of the KORG USB-MIDI Driver Tools download at the bottom of [this page](https://www.korg.com/us/support/download/driver/1/285/3541/).

#### Lights not working?

1. You can find the KORG KONTROL Editor, at the bottom of [this page](https://www.korg.com/us/support/download/product/0/159/), just above the drivers section where it says **Software**.
2. Make sure nothing else is using your device, **including MIDI Mixer!** Don't have it running while you're using the Editor.
3. In KORG KONTROL Editor, click **Common** found right under **CONTROL** and then under **LED Mode** set it to **External** instead of Internal.&#x20;
4. At the top of the screen, click **Communication** and then select **Write Scene Data**.
5. Make sure you **close** the Editor once you're done, so that the program is no longer running, otherwise MIDI Mixer will not work!

![](.gitbook/assets/image.png)

## **Application lifecycle**

A list of common questions about MIDI Mixer's versioning, release channels, and available distribution methods.

### Uninstalling

MIDI Mixer can be uninstalled in the "Apps & Features" menu in Windows for both the standalone and Microsoft Store version.

![Uninstalling MIDI Mixer in the "Apps & Features" menu in Windows 11](<.gitbook/assets/image (31) (1).png>)

When MIDI Mixer is uninstalled, however, it will leave behind some small configuration files to keep your set-up intact should you want to return to using the app at a later date.

If you want to completely remove all traces of MIDI Mixer - which is usually helpful when debugging compatibility issues - also remove all of the following folders if they exist. You can check they exist by typing the below paths in to a "Run..." dialog (Win+R):

{% hint style="warning" %}
Be aware that these files contain all of your MIDI Mixer configuration **including any custom profiles created**. Backing up these files to the cloud will be available at a later date, so make sure to [create an account](accounts/overview.md) ready.
{% endhint %}

* `%appdata%\midi-mixer-app`
* `%localappdata%\Packages\60992MIDIMixer.MIDIMixer_crf4gtfkaz836`
