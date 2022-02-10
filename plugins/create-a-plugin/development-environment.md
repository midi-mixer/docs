---
description: Set up your development environment ready to create MIDI Mixer plugins.
---

# 💻 Development environment

&#x20;MIDI Mixer supports loading JavaScript [Node.js](https://nodejs.org) plugins as a separate process that can communicate with [MIDI Mixer's plugin API](https://github.com/midi-mixer/midi-mixer-plugin).

To get started, you'll need to set up a development environment. It's recommended that you build your plugin using [TypeScript](https://www.typescriptlang.org) (JavaScript with types), giving you much better developer tooling and quality-of-life helpers such as autocomplete and static error checking.

{% hint style="info" %}
If you've already got a development environment set up with Node.js installed, skip to the next step.
{% endhint %}

### Installing Node

If you don't have Node.js installed on your system, I'd recommend installing [Volta](https://volta.sh), a toolchain manager for JavaScript that allows you to easily download and use any version of Node, NPM, or Yarn across multiple platforms.

* Follow the [Volta Getting Started Guide](https://docs.volta.sh/guide/getting-started)

### Installing an editor

[Visual Studio Code](https://code.visualstudio.com) is a very popular code editor that has fantastic support for TypeScript. If you don't get yet a code editor, I'd recommend downloading and using VSCode for getting started.

I'll be using VSCode in any demonstrations throughout this guide.

* Install [Visual Studio Code](https://code.visualstudio.com)

### That's it!

If you've done the above or already have your development environment set up, let's get started!
