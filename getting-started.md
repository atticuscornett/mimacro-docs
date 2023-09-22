# Getting Started

### Supported Microcontrollers
mimacro currently supports the following microcontrollers:
- Arduino Uno*

?> Microcontrollers with an asterisk support automatic flashing.

### Setting Up A Device

Connect your microcontroller to your computer.
Ensure no other software is using your device.
On the device page, select add device.
After a few moments, a list of connected USB devices should appear.
If your device is listed under "mimacro Devices", it is ready to be added as a device.
If your device is listed under "Compatible Devices", it is likely compatible with mimacro, but does not have firmware installed yet.
(If a compatible device supports automatic flashing, the selected device will then have mimacro firmware flashed onto it.)
If your device is listed under "Other Devices", mimacro does not recognize the device, and it may not be compatible.

?> If your device doesn't support automatic flashing or is not recognized by mimacro, you have to flash the mimacro firmware on manually. (See [list of firmware.](/firmware))

### Wiring A Device

To connect a button, connect one side to of the button to ground and the other side to a digital pin.
Buttons are read with the pin in `INPUT_PULLUP` mode.
To connect a potentiometer, wire the appropriate pins to 5V and ground, and wire the output pin to an analog pin.

?> Wiring may vary depending on the microcontroller. This section was written assuming you are using an Arduino Uno, but the process is similar for all devices.

### Configuring The Pin Layout

On the devices page, select your device. Use the dropdowns to set what part is wired into which pin. (If you have a button wired into pin 4, find the pin 4 dropdown and select button.)

?> Pin numbers are based on the internal constants used to refer to the pin on the microcontroller
This may result in different pin numbers than expected.
For example, on an Arduino Uno, pins A0-A5 are referred to as pins 14-19 in mimacro.

### Creating A Macro

On the macros page, select the + icon.
Give your macro a name. Select your device and then select the part that should trigger the macro.
Select when the part triggers the macro (e.g. when pressed down, when released, when held down).
Add actions to run when the macro is triggered.
Submit the macro when you have added the desired actions.

!> Macros with the ! icon require configuration. Configure action settings by clicking on the action title.

### Extended Functionality

You have now successfully created a macro with mimacro!
For more advanced functionality, you can try adding plugins that supercharge your productivity,