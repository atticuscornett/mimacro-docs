# Troubleshooting

Having a problem with mimacro? Here are some common solutions.

<procedure title="My device is not adding to mimacro." collapsible="true">
<step>
Check that no other software is communicating with your device (such as the Arduino IDE.)
</step>
<step>
Check that your device <a href="Supported-Microcontrollers.md">supports automatic flashing</a>.
</step>
<step>
Flash <a href="Firmware-List.md">mimacro firmware</a> to your device manually.
</step>
<step>
Restart mimacro and attempt to add the device again.
</step>
</procedure>

<procedure title="My Arduino Uno is not listed as compatible." collapsible="true">
<step>
Open the Arduino IDE.
</step>
<step>
Open the board manager on the left side of the window.
</step>
<step>
Reinstall the "Arduino AVR Boards" package. (If UAC prompt appears, allow the changes and allow any driver installations.)
</step>
<step>
Restart mimacro and attempt to add the device again.
</step>
</procedure>

<procedure title="My macros are not working." collapsible="true">
<step>
Check that the device shows as connected on the devices page. (If it is not, see next section.)
</step>
<step>
Check that the parts you are using are configured in the pin layout.
</step>
<step>
Ensure the trigger part is wired to the device properly.
</step>
<step>
If using a plugin, check plugin settings and that there is no plugin error.
</step>
</procedure>

<procedure title="Device has stopped working with mimacro." collapsible="true">
<step>
Check the device status.
</step>
<step>
If the device status is disconnected, ensure that no other program is using your microcontroller (such as Arduino IDE.)
</step>
<step>
If the device status is outdated, ensure that the latest <a href="Firmware-List.md">device firmware</a> is installed on your microcontroller.
(This should happen automatically on <a href="Supported-Microcontrollers.md">some devices</a>.)
</step>
<step>
Unplug and reconnect your device to your computer.
</step>
</procedure>