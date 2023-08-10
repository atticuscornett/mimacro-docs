# Plugin Quick Start
!> In the future, we plan to create a quick start script to make plugin creation even easier.


### Initialize `package.json` using npm
Create a folder for your plugin and use npm to set up `package.json`.
```bash
npm init
```
### Add a plugin icon
Create an icon for the plugin or use a placeholder image and put it in the plugin folder.

### Add plugin properties
Add the following properties to `package.json`:
- `displayName` - The name of the plugin that will be shown to the user
- `icon` - The path to the plugin icon, e.g. `icon.png`

### Create your plugin JavaScript
!> Important: The main javascript file must be `index.js`.

