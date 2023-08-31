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
- `options` (string[] | null) - For choice type settings, a list of human-friendly options. Otherwise null.
- `type` (string) - The type of setting (see [registerSetting])