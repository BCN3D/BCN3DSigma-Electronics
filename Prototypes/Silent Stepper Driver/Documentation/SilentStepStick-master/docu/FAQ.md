# Frequently Asked Questions

## Is the SilentStepStick 100% compatible with a StepStick or Pololu A4988?
The SilentStepStick is hardware/pin compatible with StepStick and Pololu A4988 drivers.
However the TMC2100 has different and more settings, which can be set via the CFG/MS pins.
The TMC2100 config pins also know three states: low (GND), high (VIO) and open (unconnected).
On the TMC2130 SPI is used for the configuration and so the controller board must have SPI on the CFG pins.


## Where can I find more information on the settings and operation modes?
More information can be found in the [SilentStepStick schematics](https://github.com/watterott/SilentStepStick/tree/master/hardware) and [TMC2100 datasheet](http://www.trinamic.com/products/integrated-circuits/stepper-power-driver/tmc2100) / [TMC2130 datasheet](http://www.trinamic.com/products/integrated-circuits/stepper-power-driver/tmc2130).
For most cases the **1/16 stealthChop** mode (CFG1=open, CFG2=open, CFG3=open) is suitable.
If you have problems like step losses then use the more powerful **1/16 spreadCycle** mode (CFG1=GND, CFG2=open, CFG3=open).

#### Installation Guides for 3D Printers
* [General (English)](http://reprap.org/wiki/TMC2100)
* [General (German)](http://reprap.org/wiki/TMC2100/de)
* [General (Russian)](http://3deshnik.ru/blogs/akdzg/chto-zhe-delat-belami-tmc2100)
* [RAMPS (English)](http://www.instructables.com/id/Install-and-configure-SilentStepStick-in-RAMPS-TMC/)
* [Ultimaker UMO + TMC2100 (English)](https://ultimaker.com/en/community/11571-step-by-step-installation-of-silentstepstick-drivers-on-umo)
* [Ultimaker UMO + TMC2130 (English)](https://ultimaker.com/en/community/20090-step-by-step-installation-of-sss-tmc2130-on-umo)

#### Boards with USB Power Supply
If you use a control board with USB power supply (like Arduino + RAMPS) then always ensure that ```VM``` is present, when you connect the board via USB.
Otherwise the TMC21x0 is not powered via the internal voltage regulator and a high current can flow into ```VIO``` and this can damage the internal logic.
As safety workaround you can disconnect the 5V signal in the USB cable, so that the board cannot be powered over USB.

#### RAMPS 1.4 and RUMBA Notes
If you remove all jumpers (or open all switches) for MS1+MS2+MS3, then the SilentStepStick TMC2100 driver will be in 1/16 spreadCycle mode (CFG1=GND, CFG2=open, CFG3=open), because there is a pull-down resistor on MS1 on the RAMPS.
But if you have not an original [RAMPS 1.4](http://reprap.org/wiki/RAMPS_1.4) or [RUMBA](http://reprap.org/wiki/RUMBA), then your schematics can be different and you have to check the MS-Pin configurations on you board.


## How to set the stepper motor current?
The best way to set the motor current is by measuring the voltage on the ```Vref``` pin (0...2.5V) and
adjusting the voltage with the potentiometer.
The maximum motor current is 1.77A RMS and is set via the 0.11Ohm sense resistors.

```Irms = (Vref * 1.77A) / 2.5V = Vref * 0.71```

```Vref = (Irms * 2.5V) / 1.77A = Irms * 1.41```

**Example:** A voltage of 1.0V on Vref sets the motor current to 0.71A RMS.

**Note:** On some stepper motor drivers the maximum current (e.g. A4988) is set via Vref and on others the RMS current (e.g. TMC2100).
          ```Imax = 1.41 * Irms```


## What to consider when turning the power supply on or off?
**Power on:**
The motor supply voltage ```VM``` should come up first and then ```VIO```, because the internal logic of the TMC21x0 driver is powered from ```VM```.
If you cannot ensure that ```VM``` is present before or at the same time as ```VIO``` then add a resistor with about 100-200 Ohm in series with ```VIO``` to protect the internal logic.
Only after ```VIO``` is present and stable, the driver inputs (STEP, DIR, EN, CFG1...) can be driven with a high level.

**Power off:**
If the motor is running/moving, then it is not allowed to switch off the power supply. Always make sure that the motor stands still on shutting down otherwise the TMC21x0 driver can get damaged.
An **emergency stop** can be realized, when the ```EN/CFG6``` pin is set to ```VIO```. This will switch off all power drivers and will put the motor into freewheeling.
See also: [SilentStepStick Protector with flyback diodes](https://github.com/watterott/SilentStepStick#shop)


## The motor makes noise in spreadCycle mode when it is not moving?
A motor supply voltage of 12V is in most cases to low and in general the sound gets quieter if the motor supply voltage is above 18V.


## How to control the TMC21x0 stepper motor driver?
The SilentStepStick has a normal step+direction interface.
You set the direction with the ```DIR``` pin and on every pulse on the ```STEP``` pin the motor will move one step.
Here you can find an [Arduino example](https://github.com/watterott/SilentStepStick/tree/master/software) and [Arduino library](http://www.airspayce.com/mikem/arduino/AccelStepper/) (interface=DRIVER).


## Is it possible to connect the CFG pins from different SilentStepSticks?
It is possible to connect the ```CFG``` pins from two or more driver boards.
However then the pin state can only be ```GND``` (low) or ```VIO``` (high). The open state (unconnected) is not possible in this configuration.


## Why is the TMC2100 chip on the bottom PCB side?
The TMC2100/TMC2130 chip has a thermal pad on the bottom which is soldered to the PCB.
So the thermal resistance via the chip bottom is better than via the top.
That is why the chip is on the bottom PCB side.
A heat sink can be placed directly on the PCB.
Further infos [here](https://www.youtube.com/watch?time_continue=145&v=mYuZqx8xwTg).
