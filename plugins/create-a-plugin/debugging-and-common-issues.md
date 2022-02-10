---
description: >-
  Learn how to debug your plugin, view logs, and resolve common issues during
  development.
---

# 🐛 Debugging and common issues

Most of the steps around troubleshooting are the same when creating a plugin as they are when using one.

Refer to the troubleshooting page below to see some common steps below, or continue for some development-specific errors to look out for.

{% content-ref url="../troubleshooting.md" %}
[troubleshooting.md](../troubleshooting.md)
{% endcontent-ref %}

## Common issues in development

<details>

<summary>My plugin immediately deactivates when activated</summary>

Just like Node.js, a plugin will exit if there's no reason for it to stay open. For example, a plugin that contains only one line of code (`console.log("Hello world");`) will run that line and then exit straight away.

In order to keep the process running, your code will have to be doing something long-lived to keep the [event loop](https://nodejs.dev/learn/the-nodejs-event-loop) busy.

It is also possible that your plugin is throwing an unhandled exception, causing the process to crash. In this case the error should be viewable in your plugin's log file as `%appdata%/midi-mixer-app/logs/com.myplugin.id.log`.

</details>

<details>

<summary>My dependencies aren't being included</summary>

When packing your plugin using [midi-mixer-cli](https://github.com/midi-mixer/midi-mixer-cli), you'll need to explicitly mark any dependencies you want to bundle under a `bundledDependencies` key in `package.json`.

See the [template plugin `package.json`](https://github.com/midi-mixer/plugin-template/blob/main/package.json#L27-L29) for an example.

</details>
