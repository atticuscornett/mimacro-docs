# Getting Started

> At the moment, mimacro only supports a limited selection of microcontrollers.
> You should check if your device is a [supported microcontroller](Supported-Microcontrollers.md).
> Support for more devices is planned in the future.

<procedure title="Setting Up A Device" collapsible="true">
<step>
Connect your microcontroller to your computer.

> Ensure no other software is using your device's serial connection, such as the Arduino IDE.
</step>
<step>
On the device page, select add device.
After a few moments, a list of connected USB devices should appear.
</step>
<step>
If your device is listed under "mimacro Devices", it is ready to be added as a device.
If your device is listed under "Compatible Devices", it is likely compatible with mimacro, but does not have firmware installed yet.
If your device is listed under "Other Devices", mimacro does not recognize the device, and it may not be compatible.
<tip>
If a compatible device supports automatic flashing, the selected device will then have mimacro firmware flashed onto it.
Otherwise, you will need to manually install from the <a href="Firmware-List.md">firmware list</a>.
</tip>
</step>
</procedure>

<procedure title="Wiring A Device" collapsible="true" >
<step>
To connect a button, connect one side to of the button to ground and the other side to a digital pin.
Buttons are read with the pin in <code>INPUT_PULLUP</code> mode.
</step>
<step>
To connect a potentiometer, wire the appropriate pins to 5V and ground, and wire the output pin to an analog pin.
</step>
<tip>
Wiring may vary depending on the microcontroller. This section was written assuming you are using an Arduino Uno, but the process is similar for all devices.
</tip>
</procedure>

<procedure title="Configuring The Pin Layout" collapsible="true">
<step>
On the devices page, select your device.
</step>
<step>
Use the dropdowns to set what part is wired into which pin.
<tip>
If you have a button wired into pin 4, find the pin 4 dropdown and select button.
</tip>
</step>
</procedure>

<procedure title="Creating A Macro" collapsible="true">
<step>
On the macros page, select the + icon.
</step>
<step>
Name your macro.
</step>
<step>
Select your device and select the part that should trigger the macro. 
</step>
<step>
Select when the part triggers the macro (e.g. when pressed down, when released, when held down).
</step>
<step>
Add actions to run when the macro is triggered.
<warning>
Actions with the ! icon require configuration. Configure action settings by clicking on the action title.
</warning>
</step>
<step>
Submit the macro when you have added the desired actions.
</step>
</procedure>

<procedure title="Extended Functionality With Plugins" collapsible="true">
<step>
Find a plugin you want to install.
<tip>
Try checking the <a href="https://github.com/topics/mimacro-plugin">mimacro-plugin</a> tag on GitHub.
Can't find what you want? <a href="mimacro-Plugins.md">Create your own plugin!</a>
</tip>
</step>
<step>
On the plugins page, select add plugin.
<warning>
Plugins are very powerful and can have a lot of control over your computer.
Use caution when installing plugins, and make sure you trust the developers.
</warning>
</step>
<step>
Check the plugin information and select install.
</step>
<step>
New actions should now be available when creating macros.
<tip>
Having trouble with a plugin?
Make sure you've read the README and the plugin settings are correct on the plugins page.
</tip>
</step>
</procedure>
