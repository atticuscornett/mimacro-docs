# Plugin Quick Start
!> In the future, we plan to create a quick start script to make plugin creation even easier.


### Initialize
Create a folder for your plugin and use npm to set up `package.json`.
```bash
npm init
```
### Create an Icon
Create an icon for the plugin or use a placeholder image and put it in the plugin folder.
Add an `icon` property to `package.json` with a relative path to the icon file.

### Name the Plugin
Add a `displayName` property to `package.json`. This is the name that will be displayed for your plugin.

### Create your Plugin
Now you are ready to create your plugin, which is loaded into mimacro as a node module.
For further reading, try learning about [plugin events](/plugins/events) or [functions](/plugins/events).