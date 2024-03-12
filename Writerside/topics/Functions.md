# Functions

mimacro provides functions for device communication, Node.js package sharing, plugin settings, and more.
These functions make many common plugin tasks easier.

### Storage
mimacro's storage functions give your plugin an easy way to store persistent data with a key system.

#### storage.set(plugin, key, value)
Stores the specified data at the key.

Parameters:

{type="narrow"}
plugin ([Plugin](Structures.md#plugin))
: The plugin object representing your plugin.

key (String)
: Key to store the value under.

value (any)
: The value to be stored.


### Settings