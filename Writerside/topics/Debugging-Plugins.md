# Debugging Plugins

When you are having trouble with your plugin, there are a few ways you can check
what is going wrong. The methods are generally listed in order of helpfulness and complexity.

### Method One - Running Release from Command Line

You can check the console output from your plugin using by running mimacro from the terminal.

On Windows, the mimacro binary is typically installed at `C:\Users\(user)\AppData\Local\Programs\macro\mimacro.exe` or
`C:\Users\(user)\AppData\Local\Programs\mimacro\mimacro.exe` depending on when you installed mimacro.

When you run mimacro from the command line, you can see both mimacro and plugin debug output.
This includes seeing when plugins are loaded, what files and metadata are detected, and device serial communications.

### Method Two - Using Inspection Tools

If your plugin is displaying the error status in mimacro, this means that the plugin has an error during startup.
Errors during plugin runtime typically do not display in the mimacro UI.
Startup errors can be caused by bad `package.json` configurations, running certain functions before `onEnable` is fired,
and missing required files.

First, open Electron DevTools using
<shortcut>Ctrl+Shift+I</shortcut> and open the console
You can check the details of plugin load errors in mimacro using `await electronAPI.getInstalledPlugins()`.
The plugin that is not functioning correctly will have a property called `errorDetails` that contains more information
about the plugin error.

### Method Three - Running Source from Command Line

As a last resort, you can also download mimacro's source code from [the GitHub repo](https://github.com/atticuscornett/mimacro).
This method is least recommended because it takes the most work and is not likely to produce results not
produced by [method one](#method-one-running-release-from-command-line).

In the main repo directory, run `npm install` in your terminal to install the required node packages.
(Node.js and npm must be installed to run the source code.) Next, run `npm start` to run mimacro.

<tip>
Make sure that mimacro is not running in the background when you run `npm start`.
Only one mimacro process will run at a time.
</tip>

Check the terminal output for debug information. If you are still having issues, consider looking at `plugins.js`
to check your understanding of the plugin system. You can also reach out with plugin questions at
[the GitHub repo](https://github.com/atticuscornett/mimacro).
