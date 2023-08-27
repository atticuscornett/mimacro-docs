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