---
description: How to troubleshoot a plugin that isn't working as expected.
---

# Troubleshooting

If a plugin isn't working as you expect, there are a few steps you can take as a user to figure out what's happening and hopefully fix the problem.

## Can't install plugin

If you've tried to install a plugin by running a `.midiMixerPlugin` file and it's not appearing in your UI, it's likely that there's been an issue installing it.

The first thing to do is to try and refresh the plugins list by hitting the _Refresh_ button in the UI. This will forcibly re-fetch any plugins it can find on the filesystem and should hopefully make your plugin appear.

![The highlighted &quot;Refresh&quot; icon can be seen as the looping arrows icon at the top centre of the image](../../.gitbook/assets/image%20%2815%29.png)

If this still doesn't show your plugin, you can check your app's logs to see is there have been any issues loading the files. To do this, hit `Win+R` \(or find the "Run" app in your Windows start menu\), and enter:

```text
%appdata%/midi-mixer-app/logs
```

![](../../.gitbook/assets/image%20%2811%29.png)

This will open a folder containing various log files for the application. Open up `main.log` and see if there are any recent messages that might be related to your plugin.

If you find anything of use or if you're still stuck, try chatting to the plugin developer or come and ask for help in our [Discord ](https://discord.midi-mixer.com)server.

## Plugin isn't working

If a plugin won't start then there are a few common steps that can be taken to figure out why.

### Double-check the instructions

A good plugin will have some documentation in the plugin's `PAGE.md` file, visible when looking at the plugin's **Info** tab:

![An example of the Discord plugin&apos;s &quot;Info&quot; tab, showing some set-up information](../../.gitbook/assets/image%20%2816%29.png)

### Check the settings page

A good plugin will use **Statuses** to help a user understand the current status of a plugin, as well as any issues it might be having. Check the **Settings** tab of your plugin to see if there are any error messages being displayed, or any statuses that might give a clue as to what's going wrong.

![An example of the Discord plugin showing a healthy status of &quot;Connected&quot; within the &quot;Settings&quot; tab](../../.gitbook/assets/image%20%289%29.png)

### Check the logs

If there any no statuses to check or if you're stilling having issues, you can check the internal log files of a particular plugin. To do this, hit `Win+R` \(or find the "Run" app in your Windows start menu\), and enter:

```text
%appdata%/midi-mixer-app/logs
```

![](../../.gitbook/assets/image%20%2811%29.png)

This will open a folder containing various log files for the application. The log file you're looking for will be named in the following format: `plugin.[plugin-id].log`. For example: `plugin.com.midi-mixer.discord.log`.

If you find anything of use or if you're still stuck, try chatting to the plugin developer or come and ask for help in our [Discord ](https://discord.midi-mixer.com)server.

## Developer mode

Used mainly for plugin development, **Dev Mode** opens up a live console giving you access to [Chrome DevTools](https://developer.chrome.com/docs/devtools/) to debug the plugin in real-time, as well as providing access to profiling and tracing tools.

For some plugins, you can easily click the "Dev mode" button on the plugin page itself and a console will open giving you live access to the plugin. Here you may be able to see better logs/errors.

Plugins can be built in different ways, though, meaning that dev mode requires some additional tools to be running. If dev mode doesn't appear to be working, consult the plugin's open source repository for any additional instructions regarding building the plugin or running dev mode.

