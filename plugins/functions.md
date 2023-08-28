# Functions
mimacro provides API functions that allow you to interact with devices, use common packages while using less space, manage plugin properties, and much more.

## Settings
The settings API provides an easy way to create a settings page for your plugin.
The settings you register with the settings API can be found on the plugin page of mimacro.

### registerSetting(plugin, settingID, settingLabel, settingDescription, settingType, settingDefault, [options])
!> This function has a lot of parameters right now, but will be migrated to a single object in the future.

Creates a new setting with a unique setting id for your plugin. If the id is already in use, does nothing.

Parameters:
- `plugin` ([plugin](/structures/plugin)) - Your plugin object.
- `settingID` (string) - A unique key for this setting.
- `settingLabel` (string) - The name of the setting displayed to the user.
- `settingDescription` (string) - A description of what this setting changes.
- `settingType` (string) - The type of value the setting is. (Options: `"boolean"`, `"string"`, `"choice"`, `"number"`)
- `settingDefault` (any) - The default value of a setting.
- `options` (Optional[string]) - Required only for `"choice"` type settings. A list of string options that can be selected.