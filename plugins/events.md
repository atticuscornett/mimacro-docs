# Plugin Events
Plugin events allow you to listen to when certain actions happen in the mimacro software or on mimacro devices.

You can listen to an event by writing a function matching the event name and exporting it from your module.

```javascript
function onEnable(){
    console.log("This plugin has just been enabled!");
}
modules.exports = {onEnable};
```

# onEnable([plugin](/structures/plugin))
Fires when the plugin is enabled and passes in the plugin object.

# onDisable()
Fires when the plugin is disabled.

# onDeviceMessage(message, [device](/structures/device))
Fires when mimacro receives a serial message from a device. Passes in the string contents of a message and the device that sent it.

# onSettingUpdate(settingID)
Fires when the value of a plugin [setting](/structures/setting) is updated (including by the plugin.) Passes in the id of the setting that was changed.
For creating and getting settings, see [settings functions](/plugins/functions?id=settings)

# onGetActions()
Fires when mimacro needs a list of available macro actions. Can optionally return a list of [action](/structures/action) objects that your plugin can handle.