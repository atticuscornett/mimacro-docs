# Functions
mimacro provides API functions that allow you to interact with devices, use common packages while using less space, manage plugin properties, and much more.

## Settings
The settings API provides an easy way to create a settings page for your plugin.
The settings you register with the settings API can be found on the plugin page of mimacro.

### registerSetting(plugin, settingID, settingLabel, settingDescription, settingType, settingDefault, [options])
!> This function has a lot of parameters right now, but will be migrated to a single object in the future.

Creates a new setting with a unique setting id for your plugin. If the id is already in use, does nothing.

Parameters:
- `plugin` ([plugin](/plugins/structures?id=plugin)) - Your plugin object.
- `settingID` (string) - A unique key for this setting.
- `settingLabel` (string) - The name of the setting displayed to the user.
- `settingDescription` (string) - A description of what this setting changes.
- `settingType` (string) - The type of value the setting is. (Options: `"boolean"`, `"string"`, `"choice"`, `"number"`)
- `settingDefault` (any) - The default value of a setting.
- `options` (Optional[string]) - Required only for `"choice"` type settings. A list of string options that can be selected.

### getSetting(plugin, settingID)
Get the [setting](/plugins/structures?id=settings) object with the id specified. The setting value is under the `"value"` key.

Parameters:
- `plugin` ([plugin](/plugins/structures?id=plugin)) - Your plugin object.
- `settingID` (string) - The unique key for the setting

Returns a [setting](/plugins/structures?id=settings) object.

### setSettings(plugin, settingID, value)
Sets the value of the [setting](/plugins/structures?id=setting) with the id specified. Fires [onSettingUpdate](/plugins/events?id=onsettingupdatesettingid) event.

Parameters:
- `plugin` ([plugin](/plugins/structures?id=plugin)) - Your plugin object
- `settingID` (string) - The unique key for the setting
- `value` (any) - The new setting value