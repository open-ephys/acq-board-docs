.. _statusleds:
.. role:: raw-html-m2r(raw)
   :format: html

***********************************
Status LEDs
***********************************

Each acquisition board includes 8 status LEDs with specific colors and behaviors. The LEDs do not represent a diagnostic of the actual physical hardware, but rather display what the connected software and acquisition board gateware are trying to do. The LEDs are not "manually" controlled through software, however. When the software changes a hardware setting, the LEDs just reflect these settings in different ways.

Before initializing the board by the corresponding plugin, the LED status should be considered undefined.

The colors and behaviors are as follows:

Headstage Ports
-----------------------------------

The headstage port LEDs are updated by the software port scanning process. If a headstage is manually connected or disconnected, this won't change the LED states until the next port scan.

- **RED**: No headstage is detected in this port
- **GREEN**: Headstage chip detected but acquisition is not running
- **Blinking GREEN and BLUE**: Headstage detected and acquisition is running

Digital input
-----------------------------------
- **PURPLE**: Acquisition is not running
- **Briefly flashing YELLOW**: A change has occured on a digitial input line while acquisition is running.

Digital output
-----------------------------------
- **PURPLE**: Default state; does not change.

Analog Output
-----------------------------------
- **PURPLE**: Acquisition is not running OR all DACs disabled
- **Blinking GREEN and BLUE**: Some DACs are enabled and acquisition is running

Analog Input
-----------------------------------
- **PURPLE**: Acquisition is not running
- **Other colors**: Acquisition is running. Depends on the input channel whose absolute value is highest:

  - If the signal is positive, the color ranges from dim white (0V) to light red (5V)
  - If the signal is negative, the color ranges from dim white (0V) to light green (5V)

|
