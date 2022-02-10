---
description: >-
  Add assignments to your plugin that your users can select and control with
  faders and buttons.
---

# 🎚 Assignments

The most common action for a plugin to perform is adding assignments. These are entries that appear in the list when assigning a [Group](../../terminology.md#groups).

![The "Example Plugin Entry" assignment created by the MIDI Mixer Template Plugin](<../../.gitbook/assets/image (47).png>)

Once an assignment is created, we can use code to affect the controlling [Group](../../terminology.md#groups)'s state and react to changes from the user.

## Create an assignment

Using [midi-mixer-plugin](https://github.com/midi-mixer/midi-mixer-plugin), it's easy to use the underlying MIDI Mixer API to register assignments.

```typescript
/**
 * Example of setting up an assignment to be controlled by the plugin.
 */
const myAssignment = new Assignment("foo", {
  name: "Example Plugin Entry",
});
```

The above code creates a new `Assignment` with a user-facing name of `"Example Plugin Entry"`.

The first argument to the constructor (`"foo"`) is the assignment's ID. This is important to keep standardised, as this is used internally to manage what the user has assigned their [Group](../../terminology.md#groups) to, ensuring that the assignment is correctly remembered as your plugin activates, loads, or deactivates.

The second argument is an object containing any values that the assignment should start with, such as mute status or volume level. The available parameters mirror some of the parameters we can set at any time once the assignment is created:

* `name`\
  The name of the assignment within MIDI Mixer.\

*   `assigned`\
    The initial assigned status of the entry.

    Defaults to `false`.\

*   `muted`\
    The initial assigned status of the entry.

    Defaults to `false`.\

*   `running`\
    The initial running status of the entry.

    Defaults to `false`.\

*   `throttle`\
    ``The minimum amount of time in milliseconds between volume change updates from MIDI Mixer. Some faders are very granular, so throttling these updates is sensible to ensure the good performance of plugins.

    Accepted values are anything between `50` to `1000`.

    Defaults to `50`.\

*   `volume`\
    The initial volume level that the entry has, between `0` and `1`.

    Defaults to `1`.

## Update an assignment

Once an assignment has been created, you can update it at any time using the same parameters as above. For example:

```typescript
myAssignment.name = "A Different Plugin Entry";
myAssignment.muted = true;
myAssignment.volume = 0.2;
```

In addition to the properties above, you can also set the `meter` property.

This property is similar to the `volume` property: a value between `0` and `1` that represents the Group's current peak meter level. It is described as:

> The current indicator level for meters. Setting this updates the entry's meter level for the next 150ms before falling off or being updated again.

Setting it is as easy as the others:

```typescript
myAssignment.meter = 0.5;
```

## React to changes

In order to react to user input, we can use event listeners to run functions on certain events occurring.

```typescript
myAssignment.on("volumeChanged", (level: number) => {
  console.log("User changed the volume to:", level);
});
```

This simple example listens for the user changing their volume level and logs what the new level is.

In reality, here you would update whatever source you are affecting, then set `myAssignment.volume` to the proper level after you've made your change.

At present there are four events to listen to on an assignment:

* `volumeChanged` - `(level: number) => void`
* `mutePressed` - `() => void`
* `assignPressed` - `() => void`
* `runPressed` - `() => void`

## Remove an assignment

Removing an assignment is as easy as creating one.

```typescript
myAssignment.remove();
```

{% hint style="warning" %}
After calling `.remove()`, setting properties will no longer cause any action, and listeners will no longer trigger. It's recommended that you dereference the assignment so that it can be garbage collected.
{% endhint %}
