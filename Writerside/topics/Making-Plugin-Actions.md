# Making Plugin Actions

Let's make our first action using the mimacro plugin API.
This tutorial assumes that you have already completed the steps in [creating a plugin](Creating-A-Plugin.md)
and know how to package your plugin.

### The Event System

The event system is the main way that plugins interface with mimacro.
A plugin can register to listen to an event by creating a function with the event name and exporting it from your module.
The events that are most relevant to this tutorial are `onEnable`, `onDisable`, `onGetActions`, and `onAction`. For more
information about the event system and available events, see the [events page](Events.md).

### Listening to Events

The easiest events to listen to are `onEnable` and `onDisable`.
These events do not require any information to be returned. The `onEnable` event
does give us an object as input, but we can ignore it for this tutorial.

The `onEnable` event fires when the plugin is loaded and mimacro is ready to use it.
The `onDisable` event fires when the plugin is disabled or mimacro is quit, meaning the plugin should stop its work.

Here is an example of listening to these events:
```Javascript
// Runs on plugin load.
function onEnable(){
    console.log("My plugin has been enabled!");
}

// Runs when plugin should quit.
function onDisable(){
    console.log("My plugin has been disabled.");
}

// Register functions as event listeners for mimacro.
module.exports = {onEnable, onDisable};
```

This code works fine, but it doesn't actually add features to mimacro.

### Listing Available Actions

The first thing you need to do to create a custom action is to tell mimacro what actions our plugin has.
To do this, you listen to the `onGetActions` event and return a list your plugin's actions.

An action is represented as an object with these properties:

{type="narrow"}
displayName
: The human name of the action.

id
: A unique key for the action.

ui
: A list of the UI components/settings for the action. **Leave empty if no UI input is required.**

This creates a function that looks something like this:
```Javascript
function onGetActions(){
    return [
        {
            "displayName": "My First Action",
            "id": "first-action",
            "ui": []
        }
    ]
}
```
> Don't forget to add this function to your `module.exports`, or this code won't work!

If you package and load your plugin now, you should see new action options when creating a macro.
However, the action still doesn't do anything yet.

### The Action

To run an action, you need to listen to the `onAction` event.
The `onAction` event passes two parameters, the first being the id of the action to be triggers
and the second being the UI setting inputs (discussed later.)

The plugin API provides numerous helpful functions that make code more efficient.
One of these functions is `use`, which allows you to borrow libraries used by mimacro as a replacement for `require`.
This helps keep plugin sizes small and reduces library redundancy.
One of the libraries provided by `use` is [nut.js](https://nutjs.dev/), a desktop automation library.
We will use nut.js to type a message.

Here is some code that will type "Hello, world!" when used in a macro:
```Javascript
// Import keyboard from nut.js
const {keyboard} = use("@nut-tree/nut-js");

// Function can be sync or async
async function onAction(actionID){
    if (actionID === "first-action"){
        await keyboard.type("Hello, world!");
    }
}
```
> Don't forget to add this function to your `module.exports`, or this code won't work!

If we create a macro that uses the action now, we can see "Hello, world!" is typed.

### Advanced Actions

Some actions require additional input to work, such as a message to type or a key to press.
mimacro's plugin API lets you specify the inputs your action needs with the `ui` property.
The `ui` property is a list of [ActionUI](Structures.md#actionui) objects to show the user.

ActionUI objects have the following properties:

{type="narrow"}
id
: Unique id for the ActionUI object.

label
: Input label to show to the user.

type
: The type of input. Can be `"string"`, `"number"`, `"options-select"`, or `"checkbox"`.

options
: Required for `"options-select"` type. List of strings to be shown as options.

Let's make another action that will type whatever messages the user specifies.

First, we will add a new action to `onGetActions`.

```Javascript
function onGetActions(){
    return [
        {
            "displayName": "My First Action",
            "id": "first-action",
            "ui": []
        },
        // New action
        {
            "displayName": "Type a Message",
            "id": "type-message",
            "ui": [
                {
                    "id": "message",
                    "label": "Message to type",
                    "type": "string"
                }
            ]
        }
    ]
}
```

Next, we need to modify our `onAction` function.
The second parameter `onAction` receives is an object with the UI ids as keys.

```Javascript
// Note the new parameter.
function onAction(actionID, actionSettings){
    if (actionID === "first-action"){
        await keyboard.type("Hello, world!");
    }
    // New action
    if (actionID === "type-message"){
        await keyboard.type(actionSettings["message"]);
    }
}
```

We can now create advanced actions with user input!
For plugins with global persistent settings, see [making plugin settings](Making-Plugin-Settings.md).