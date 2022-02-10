---
description: The manifest file for our MIDI Mixer plugin.
---

# 📄 plugin.json

The `plugin.json` file (also known as the "manifest") in the root of your plugin is used to tell MIDI Mixer some basic information about the plugin, as well as what can be configured. It provides:

* `id` A unique ID for the plugin in [reverse domain name notation](https://en.wikipedia.org/wiki/Reverse\_domain\_name\_notation)
* `name` The name of the plugin as it appears in the UI
* `version` The version of the plugin, shown to the user but used for releases in the future
* `author` The author of the plugin (that's you!)
* `main` The file to load to start the plugin
* `icon` A path to the icon to display next to the plugin for buttons, assignments, and other lists
* `settings` Settings for your plugin that are set by the user and accessible in code (see the Settings page for the schema)

{% hint style="info" %}
This file must be placed in the root of your plugin so that MIDI Mixer can access it.
{% endhint %}

### Example

Here's an example of a basic `plugin.json` pulled from the [MIDI Mixer Template Plugin](https://github.com/midi-mixer/plugin-template).

{% hint style="info" %}
The `$schema` key below provides autocompletion and validation when editing this file. You can reference your local `midi-mixer-plugin` package as below or use a service such as [Skypack](https://cdn.skypack.dev/midi-mixer-plugin@latest/plugin.schema.json) to always reference the latest version.
{% endhint %}

```json
{
  "$schema": "./node_modules/midi-mixer-plugin/plugin.schema.json",
  "id": "com.midi-mixer.template",
  "name": "Template Plugin",
  "type": "node",
  "version": "1.0.1",
  "author": "MIDI Mixer",
  "main": "lib/main.js",
  "settings": {
    "text": {
      "label": "A text field",
      "type": "text",
      "required": false
    }
  }
}
```

Next, let's have a look at how to add assignments so our users can control our plugin with faders and buttons.
