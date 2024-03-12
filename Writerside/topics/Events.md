# Events

The plugin event system allows your plugin to subscribe to events that happen in mimacro
or with mimacro devices. Events are a fundamental part of the plugin system and are used to 
integrate actions with mimacro. For a beginner-friendly intro to using the plugin system, see 
[making plugin actions](Making-Plugin-Actions.md).

You can listen to an event by writing a function matching the event name and exporting it from your module.

```Javascript
function onEnable(){
    console.log("This plugin has just been enabled!");
}
module.exports = {onEnable};
```

### onEnable([plugin](Structures.md#plugin))
Fires when the plugin is first installed, mimacro starts, or the plugin is re-enabled.
Passes in the [plugin object](Structures.md#plugin) required by some functions.

### onDisable()
Fires when the plugin is disabled or mimacro is quit.

### onGetActions()
Fires when mimacro is compiling a list of available actions for the user.
Can return a list of [action](Structures.md#action) objects your plugin handles.

> For more information about handling plugin actions, see [making plugin actions](Making-Plugin-Actions.md).

### onAction(actionID, actionSettings)
Fires when an action handled by your plugin is triggered.
Passes in the id of the action triggered and the settings for the action as an object with the setting ids as keys.

### onDeviceMessage(message, [device](Structures.md#device))
Fires when a mimacro device sends a serial message.
Passes in the serial message as a string and the device that sent it as a [device object](Structures.md#device).

### onSettingUpdate(settingID)
Fires when a plugin setting is updated (whether by the user or the plugin).
Passes in the id of the setting that has been updated.

> For more information about managing plugin settings, see [making plugin settings](Making-Plugin-Settings.md).