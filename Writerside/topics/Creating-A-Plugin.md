# Creating a Plugin

> In the future, we plan to create a quick start script to make plugin creation even easier.
{style="note"}

### Initialize
Create a folder for your plugin and use npm to set up `package.json`.
```bash
npm init
```
### Create an Icon
Create an icon for the plugin or use a placeholder image and put it in the plugin folder.
Add the `icon` property to `package.json` with a relative path to the icon file.

### Name the Plugin
Add the `displayName` property to `package.json`. This is the name that will be displayed for your plugin.

### Specify Plugin Version
Add the `pluginAPIVersion` property to `package.json` to specify the target [mimacro plugin API version](Plugin-API-Versions.md).

### Packaging your Plugin
To bundle your plugin into a compatible plugin file, put all of your plugin files in the top level of a `.zip`.

### Create your Plugin
Now you are ready to create your plugin, which is loaded into mimacro as a node module.
For further instructions, try reading [](Making-Plugin-Actions.md) or [](Making-Plugin-Settings.md).
