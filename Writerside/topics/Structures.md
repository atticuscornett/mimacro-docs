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
A device object contains information about mimacro devices 
connected to the software.

{type="narrow"}
friendlyName (String)
: Human-friendly device name (supplied by device, not the user.)

manufacturer (String)
: The device manufacturer.

mimacroType (String)
: Type of mimacro device, e.g. 'Arduino Uno.'

mimacroVersion (String)
: Version of mimacro firmware the device runs.

nickname (String)
: The name the user gives the device.

pinOut ([PinOut](#pinout))
: The configuration of the device ports.

pinProperties ([PinProperties](#pinproperties))
: The advanced settings set for the device pins.

port (String)
: The USB port the device is in.

status (String)
: The current state of the device (e.g. "connected", "disconnected", "updating", "outdated").

### Action
An action object contains information about an action a plugin can handle.

displayName (String)
: The action name displayed to the user

id (String)
: A unique id for the action

ui ([ActionUI[]](#actionui))
: An list of ActionUI objects to show to the user.

### ActionUI
An object with action settings to show to the user.

id (String)
: Unique id of the ActionUI.

label (String)
: Name of setting displayed to user.

type (String)
: Type of setting. Can be `"string"`, `"number"`, `"options-select"`, or `"checkbox"`.

options (String[], optional)
: Required for `"options-select"` type. List of strings to be shown as options.

required (Boolean, optional)
: Whether the value must be set by the user. Defaults to `true` if not set.

### PinOut
A PinOut object contains the port configuration of a mimacro device.

analog (Number[])
: List of device analog pin configuration states.
(Convert ids to parts using [parts.json](https://github.com/atticuscornett/mimacro/blob/main/parts.json).)

digital (Number[])
: List of device digital pin configuration states.
(Convert ids to parts using [parts.json](https://github.com/atticuscornett/mimacro/blob/main/parts.json).)

### PinProperties

A PinProperties object contains the advanced settings for each pin of a mimacro device.

analog (object)

: Advanced settings for analog pins.

: Object properties:
- minChange (Number) - The minimum value change for the analog pin to update.
- timeout (Number) - The minimum amount of time between analog pin updates.

digital (object)
: Advanced settings for digital pins.

: Object Properties:
- timeout (Number) - The minimum amount of time between digital pin updates.