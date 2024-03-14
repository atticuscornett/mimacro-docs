# Structures

mimacro uses a number of different object structures for different
purposes. Below is a list of these structures and their properties.

### Plugin
A Plugin object holds information about a plugin and is used by
numerous plugin API functions.

{type="narrow"}
author (String)
: Name of the plugin author.

description (String)
: Description of the plugin.

packageName (String)
: Unique node package name for the plugin.

pluginName (String)
: The human-friendly plugin name displayed to the user.

version (String)
: Plugin package version.

### Setting
A Setting object holds the configuration of a plugin setting to show
to the user.

{type="narrow"}
id (String)
: Unique id of the setting.

label (String)
: Name of setting displayed to user.

description (String)
: Description of what the setting does.

type (String)
: Type of setting. Can be `"boolean"`, `"string"`, `"choice"`, or `"number"`.

default (any)
: Default value of the setting.

options (String[], optional)
: Required for `"choice"` type. List of string options.

### SettingValue
A SettingValue object holds the value of a setting.

{type="narrow"}
label (String)
: Name of setting displayed to user.

description (String)
: Description of what the setting does.

type (String)
: Type of setting. Can be `"boolean"`, `"string"`, `"choice"`, or `"number"`.

options (String[], optional)
: Required for `"choice"` type. List of string options.

value (any)
: Value the setting is set to.


### Device

### Action

### ActionUI

### PinOut

### PinProperties