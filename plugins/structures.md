# Object Structures

## Plugin
A plugin object contains information about a plugin that can be used with certain plugin API functions.

Properties:
- `author` (string) - Name of the plugin author
- `description` (string) - Description of the plugin
- `packageName` (string) - Unique node package name for the plugin
- `pluginName` (string) - The human-friendly plugin name displayed to the user
- `version` (string) - Package semver

## Setting
A setting object contains the configuration and current value of a plugin setting.

Properties:
- `description` (string) - A description of what the setting changes
- `label` (string) - A human-friendly name for the plugin
- `options` (string[] | null) - For choice type settings, a list of human-friendly options. Otherwise, null.
- `type` (string) - The type of setting (see registerSetting)

## Device
A device object contains information about mimacro devices connected to the software.

Properties:
- `friendlyName` (string) - Human-friendly device name (supplied by device, not the user)
- `manufacturer` (string) - The device manufacturer
- `mimacroType` (string) - Type of mimacro device, e.g. `'Arduino Uno'`
- `mimacroVersion` (string) - Version of mimacro firmware the device runs
- `nickname` (string) - The name the user gives the device
- `pinOut` ([pinOut](/plugins/structures?id=pinOut)) - The configuration of the device ports
- `pinProperties` ([pinProperties](/plugins/structures?id=pinProperties)) - The advanced settings set for the device pins
- `port` (string) - The USB port the device is in
- `status` (string) - The current state of the device (e.g. `"connected"`, `"disconnected"`, `"updating"`, `"outdated"`)

## Action
An action object contains information about an action a plugin can handle.

Properties:
- `displayName` (string) - The action name displayed to the user
- `id` (string) - A unique id for the action
- `ui` (object) - An object that with string keys that are used as ids for [ActionUI](/plugins/structures?id=actionui)

## ActionUI
An action UI object contains a setting for an action.

Properties:
- `type` (string) - The type of setting. Can be `"string"`, `"number"`, `"options-select"`, `"checkbox"`.
- `options` (string[] | null) - If type is `"options-select"`, must be a list of string options. Otherwise, null.

## pinOut
A pinOut object contains the port configuration of the mimacro device.

Properties:
- `analog` (number[]) - List of device analog pin configuration states (Convert ids to parts using [parts.json](https://github.com/atticuscornett/mimacro/blob/main/parts.json))
- `digital` (number[]) - List of device digital pin configuration states (Convert ids to parts using [parts.json](https://github.com/atticuscornett/mimacro/blob/main/parts.json))

## pinProperties
A pinProperties object contains the advanced settings for each pin of the mimacro device.

Properties:
- `analog` (object) - Advanced settings for analog pins

    Properties: 
    - `minChange` (number) - The minimum value change for the analog pin to update
    - `timeout` (number) - The minimum amount of time between analog pin updates

- `digital` (object) - Advanced settings for digital pins

    Properties:
    - `timeout` (number) - The minimum amount of time between digital pin updates 