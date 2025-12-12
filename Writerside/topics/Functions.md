# Functions

mimacro provides functions for device communication, Node.js package sharing, plugin settings, and more.
These functions make many common plugin tasks easier.

### Utilities

Utility functions help accelerate development and optimize your plugin
but don't fit in to any other category.

#### sendMessageToDevice(device, message)
Send a serial message to a connected device.

{type="narrow"}
device ([Device](Structures.md#device))
: The device to send the message to.

message (String)
: The message to send to the device.

#### use(package)
Use a Node.js package provided by mimacro.
Works just like `require` in Node.

##### Provided Modules {collapsible="true"}
As of [API version](Plugin-API-Versions.md) 2, mimacro provides the following packages:
- "@jitsi/robotjs": "^0.6.13"
- "@sienci/avrgirl-arduino": "^5.0.3"
- "adm-zip": "^0.5.10"
- "loudness": "^0.4.2"
- "marked": "^12.0.0"
- "uuid": "^9.0.0"

{type="narrow"}
package (String)
: The Node.js package to use.

### Storage
mimacro's storage functions give your plugin an easy way to store persistent data with a key system.

#### storage.set(plugin, key, value)
Stores the specified data at the key.

{type="narrow"}
plugin ([Plugin](Structures.md#plugin))
: The plugin object for your plugin.

key (String)
: Key to store the value under.

value (any)
: The value to be stored.

#### storage.get(plugin, key)
Gets the value at the key.
Returns the value.

{type="narrow"}
plugin ([Plugin](Structures.md#plugin))
: Your plugin object.

key (String)
: Key the value is stored under.


### Settings

mimacro's setting functions create and manage user-controlled settings shown on the 
plugins page. For step-by-step instructions, see [making plugin settings](Making-Plugin-Settings.md).

#### registerSettingObj(plugin, settingObj)
Register a plugin setting to show on the settings page.

{type="narrow"}
plugin ([Plugin](Structures.md#plugin))
: Your plugin object.

settingObj ([Setting](Structures.md#setting))
: The setting to show to the user.

#### getSetting(plugin, settingID)

Get the value of a setting.
Returns a [SettingValue](Structures.md#settingvalue) object.

{type="narrow"}
plugin ([Plugin](Structures.md#plugin))
: Your plugin object.

settingID (String)
: The unique key of a setting.

#### setSetting(plugin, settingID, value)

Set the value of a setting.
Returns setting value.

{type="narrow"}
plugin ([Plugin](Structures.md#plugin))
: Your plugin object.

settingID (String)
: The unique key of a setting.

value (any)
: The value to set the setting to.

#### registerSetting(plugin, settingID, settingLabel, settingDescription, settingType, settingDefault, [options])

> This function is deprecated and may be removed in future API versions.
>
{style="warning"}

{type="narrow"}
plugin ([Plugin](Structures.md#plugin))
: Your plugin object.

settingID (String)
: A unique key for this setting.

settingLabel (String)
: The name of the setting displayed to the user.

settingDescription (String)
: A description of what this setting changes.

settingType (String)
: The type of value the setting is. (Options: "boolean", "string", "choice", "number")

settingDefault (any)
: The default value of a setting.

options (Optional[String])
: Required only for "choice" type settings. A list of string options that can be selected.