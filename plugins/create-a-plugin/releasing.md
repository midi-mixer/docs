---
description: Create a midiMixerPlugin file to distribute your plugin to other users.
---

# 🚚 Releasing

MIDI Mixer plugins can be distributed using `.midiMixerPlugin` files, which users can then use to install plugins quickly and easily.

{% hint style="info" %}
See the [Installing a Plugin](../use-a-plugin.md#installation) section to see the user experience for this.
{% endhint %}

This is done using [midi-mixer-cli](https://github.com/midi-mixer/midi-mixer-cli), which gives us the `midi-mixer pack` command. This verifies the shape of your plugin and packages it up so it can be quickly and easily installed by other users.

A common workflow in order to version your plugin and generate a `.midiMixerPlugin` looks like:

1. Change the version your `package.json` file using `npm version`
2. Build your code
3. Run `midi-mixer pack`

NPM scripts are set up in the [template plugin](https://github.com/midi-mixer/plugin-template) that mean this process looks like:

1. `npm version [<newversion> | major | minor | patch]`
2. `npm run build`
3. `npm run dist`

Once that's complete, you should have generated a file that looks like `com.myplugin.id.1.0.0.midiMixerPlugin`.

Double click this to install, or pass to other users for them to install!

{% hint style="warning" %}
Note that a common mistake is to miss bundling dependencies in to this file. See "[My dependencies aren't being included](debugging-and-common-issues.md#common-issues-in-development)" for how to bundle them using `midi-mixer pack`.
{% endhint %}
