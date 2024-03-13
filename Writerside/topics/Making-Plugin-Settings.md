# Making Plugin Settings

Sometimes plugins need to use global settings to control their behavior.
The plugin API supplies a few useful functions and events to make settings easy
to implement.

Let's say our plugin needs to connect to a server.

### Registering Plugin Settings

First, we need to catch the plugin object that is passed in the `onEnable` event.
The plugin object must be passed to numerous functions we will be using.

```Javascript
let plugin;

function onEnable(pluginObj){
    plugin = pluginObj;
}
```

Next, we use the `registerPluginObj` function in `onEnable` to register a plugin setting.
`registerPluginObj` takes two parameters, the plugin object and a [setting object](Structures.md#Setting).

A plugin setting object has the following properties:

{type="narrow"}
id
: Unique id of the setting.

label
: Name of setting displayed to user.

description
: Description of what the setting does.

type
: Type of setting. Can be `"boolean"`, `"string"`, `"choice"`, or `"number"`.

default
: Default value of the setting.

options
: Required for `"choice"` type. List of string options.

Creating a server connection option would look something like this.

```Javascript
let plugin;
function onEnable(pluginObj){
    plugin = pluginObj;
    registerSettingObj(plugin, {
        "id": "url",
        "label": "Server URL",
        "description": "The server URL to connect to. 'localhost' for most setups."
        "type": "string",
        "default": "localhost"
    });
}
```

If we install our new plugin and reload the plugins page, we now see a settings option for our plugin.

### Getting Setting Values

To get the value of a setting, we use the `getSetting` function.
`getSetting` takes two parameters, the plugin object and the setting id.

The `getSetting` function returns a [SettingValue](Structures.md#SettingValue) object with these properties:

{type="narrow"}
value
: Current value of the setting.

label
: Name of setting displayed to user.

description
: Description of what the setting does.

type
: Type of setting. Can be `"boolean"`, `"string"`, `"choice"`, or `"number"`.

options
: Required for `"choice"` type. List of string options.

Grabbing the value of a setting looks like this:
```Javascript
let serverURL = getSetting(plugin, "url").value;
```

### Listening to Setting Changes

The plugin API provides an easy way to listen to when a setting changes using the `onSettingUpdate` event.
The `onSettingUpdate` event gives the id of the setting updated as a parameter.
You must still use `getPlugin` to read the value of the plugin.

```Javascript
function onSettingUpdate(updatedSetting){
    let newSettingValue = getSetting(plugin, updatedSetting).value;
}
```

> As with all event listeners, add this function to `module.exports`.

You can now make more advanced plugins with persistent settings.
To learn about catching errors in your plugin, see [how to debug your plugin](Debugging-Plugins.md).