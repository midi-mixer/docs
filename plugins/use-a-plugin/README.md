# Use a plugin

## Installation

Plugins are registered by extracting their built files in to `%appdata%/midi-mixer-app/plugins`. A plugin's page will usually include instructions for how to download and extract the plugin to the correct location.

The most important detail is that a `plugin.json` file is in the root of the extracted plugin.

For example, an extracted plugin named `com.midi-mixer.discord` would have the following file tree:

```text
midi-mixer-app/
├─ plugins/
│  ├─ com.midi-mixer.discord/
│  │  ├─ plugin.json
│  │  ├─ ...other files...
```

Once you've extracted the files, head in to the plugins UI and hit the refresh button to see your new plugin!

![The &quot;Refresh&quot; button is highlighted at the top centre of the image](../../.gitbook/assets/image%20%2813%29.png)

If you don't see your plugin after hitting the refresh button or you're having other issues, check the [troubleshooting ](troubleshooting.md)guide.

## Simpler installs

Currently being testing in the `v2.4.0` beta is `.midiMixerPlugin` files. This is a much simpler method of installing plugins that involves running the given file and nothing else.

This also gives plugin developers a much easier way to build and distribute their plugins, as the CLI tool to build the files \([midi-mixer-cli](https://www.npmjs.com/package/midi-mixer-cli)\) will not only package the files, but also verify that they're valid and runnable by MIDI Mixer.

![An example Discord plugin using the new &quot;.midiMixerPlugin&quot; format](../../.gitbook/assets/image%20%287%29.png)

Keep an eye on the [release notes ](https://releases.midi-mixer.com)for when this new format drops.



