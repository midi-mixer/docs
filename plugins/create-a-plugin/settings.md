---
description: Provide your user with settings to customise your plugin.
---

# 🎛 Settings

MIDI Mixer provides you with the ability to specify a list of settings in a standardised format to allow the user to customise your plugin's functionality.

There are currently four types of settings that can be defined, with more planned in later releases.

* Text field
* Password field (a text field with obscured input)
* Status field (a customisable message to show to the user)
* Button (react to presses to trigger actions within your plugin)

![The Brightness plugin using a status field to show the user how many monitors have been detected](<../../.gitbook/assets/image (31).png>) ![The Philips Hue plugin using a text field and password field to allow user input](<../../.gitbook/assets/image (39).png>)

## Manifest schema

To provide these settings to a user, you can add them to your `plugin.json` file. This will automatically add the settings to the MIDI Mixer UI and allow you to access the user's input within your plugin's code.

The example `plugin.json` snippet below adds one of every type of input.

```json
{
  "settings": {
    "foo": {
      "label": "A text field",
      "type": "text",
      "fallback": "FOO"
    },
    "bar": {
      "label": "A password field",
      "type": "password"
    },
    "baz": {
      "label": "Press this button",
      "type": "button"
    },
    "qux": {
      "label": "We are currently connected",
      "type": "status"
    }
  }
}
```

This produces the following settings page for the user:

![The settings page produced for the user with the above plugin.json snippet](<../../.gitbook/assets/image (41).png>)

Let's note a few things about each input field:

* **"A text field"**\
  The field has used the `"fallback"` value of `"FOO"` because the user hasn't entered anything. This is displayed using the input's placeholder.\

* **"A password field"**\
  This field has no fallback, so remains empty.\

* **"Press this button"**\
  The button has used the `"label"` text as it's call-to-action. We'll use this button later to trigger an event in our code.\

* **"Player level"**\
  This small piece of status text has used the `"label"` value and the `"fallback"` value to default to `Player level: 1`. We'll adjust this dynamically in code later.

Let's move to our `main.ts` file next and have a look at how to retrieve and affect these settings in code.

## Retrieving settings in code

After the user has entered their settings, we can retrieve them for our plugin to use.

We'll use the [midi-mixer-plugin](https://github.com/midi-mixer/midi-mixer-plugin) library to provide us with a `$MM` object we can use to interact with MIDI Mixer's API.

{% hint style="info" %}
The `midi-mixer-plugin` library is pre-installed if you're using the plugin template. If you're starting from scratch, you can install it using `npm install midi-mixer-plugin`.
{% endhint %}

Let's add a `console.log` to our plugin that retrieves and logs the settings our user has input.

```typescript
import * as midiMixer from "midi-mixer-plugin";

$MM.getSettings().then((settings) => {
  console.log("Current settings:", settings);
});
```

Build the app (using `npm run build` or `npm run build:watch`) and load the plugin in dev mode using by clicking the "Disabled" text next to the "Dev mode" header. ![](<../../.gitbook/assets/image (45).png>)

This should produce some output like this:

![The debugging tools for a MIDI Mixer plugin, showing welcome text and some settings](<../../.gitbook/assets/image (50).png>)

Here, we can see some welcome text to help get you oriented with Node.js debugging tools, along with our log of the current settings.

As the user hasn't filled anything out yet, we can see that `foo` (our text field) has fallen back to the `"FOO"` value, `bar` (our password field) has an empty value, and `qux` has fallen back to a value of `"1"`.

If the user fills these settings in and reloads the plugin, the logged values here will change accordingly.

Next, let's look at reacting to users pressing buttons, and displaying helpful messages in return.

## Reacting to buttons and using statuses

Buttons can be used to listen for user input and statuses can be used to show the user what is happening internally.

First, let's write some code to listen for a user hitting our `baz` button in the example above.

```typescript
$MM.onSettingsButtonPress("baz", () => {
  console.log("The baz button was pressed!");
});
```

With the above code, we run a function every time the `baz` button is pressed, which sends a log to our debug console.

If we rebuild and reload the plugin, we should now receive that message in our console!

![The "The baz button was pressed!" message appearing in the console after clicking the button on the settings page](<../../.gitbook/assets/image (32).png>)

Fantastic!

Now that we can react to button presses, let's add some more code there to update the "Player level" status to `"9001"` when the button is pressed.

```typescript
$MM.onSettingsButtonPress("baz", () => {
  $MM.setSettingsStatus("qux", "9001");
});
```

Hey presto, now clicking our button changes the status message in the settings page!

![The "Player level" status message showing "9001" after pressing the button on the settings page](<../../.gitbook/assets/image (36).png>)

{% hint style="info" %}
Future releases of MIDI Mixer's Plugin API are expected to contain bidirectional settings (where you can retrieve and set all settings) and more input types.
{% endhint %}
