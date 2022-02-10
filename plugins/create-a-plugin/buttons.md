---
description: Add buttons to your plugin so users can select and trigger one-time actions.
---

# 🔘 Buttons

Buttons are entries that appear in the list when assigning a particular [Button](../../terminology.md#buttons) to an action. Built-in buttons are small tasks such as "Play media" or "Set default output device".

![The "Example Button Type" button created by the MIDI Mixer Template Plugin](<../../.gitbook/assets/image (48).png>)

Adding your own buttons allows the user to manually trigger one-time actions within your plugin.

## Create a button

Using [midi-mixer-plugin](https://github.com/midi-mixer/midi-mixer-plugin), it's easy to use the underlying MIDI Mixer API to register new buttons.

```typescript
/**
 * Example of setting up a button type to be controlled by the plugin.
 */
const myButton = new ButtonType("bar", {
  name: "Example Button Type",
});
```

The above code creates a new `ButtonType` with a user-facing name of `"Example Button Type"`.

The first argument to the constructor (`"bar"`) is the button's ID. This is important to keep standardised, as this is used internally to manage what the user has assigned their [Button](../../terminology.md#buttons) to, ensuring that the button is correctly remembered as your plugin activates, loads, or deactivates.

The second argument is an object containing any values that the assignment should start with: `name` and `active`. The available parameters mirror the parameters we can set at any time once the button is created:

*   `name`\
    The name of the entry that will appear in MIDI Mixer. It will also be marked with the name of the plugin.

    Blank names are not allowed.\

*   `active`\
    The initial indicator status of the entry.

    Defaults to `false`.

## Update a button

Once a button has been created, you can update it at any time using the same parameters as above. For example:

```typescript
myButton.name = "A Different Button Type";
myButton.active = true;
```

## React to presses

In order to react to user input, we can use event listeners to run a function when the button is pressed.

```typescript
myButton.on("pressed", () => {
  console.log("User pressed the button!");
});
```

This simple example listens for the user pressing the button, then logs that the button has been pressed.

## Remove a button

Removing a button is as easy as creating one.

```typescript
myButton.remove();
```

{% hint style="warning" %}
After calling `.remove()`, setting properties will no longer cause any action, and listeners will no longer trigger. It's recommended that you dereference the button so that it can be garbage collected.
{% endhint %}
