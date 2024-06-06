# Plugin API Versions
To specify the API version your plugin targets, set the `pluginAPIVersion` property of your plugin's
`package.json`, e.g. `"pluginAPIVersion": 1`. If no plugin API version is
specified, value of `1` is assumed.

## Version 2
> This version is upcoming and introduces breaking changes.
{style="warning"}

Supported mimacro versions: TBA

Introduced: TBA

### Breaking Changes

- [use](Functions.md#use-package) now provides `"@jitsi/robotjs": "^0.6.13"` instead of `"@nut-tree/nut-js": "^4.0.0"`.
Keyboard and mouse controlling plugins must be changed accordingly.
- `pluginAPIVersion` key must now be supplied in `package.json` for plugin to run.

### Other Changes

## Version 1
Supported mimacro versions: `1.0.0` to `1.0.1`

Introduced: Oct 28, 2023

Deprecated: TBA