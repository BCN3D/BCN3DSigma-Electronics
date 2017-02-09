# SilentStepStick
The Silent-Step-Stick is a Stepper Motor Driver Board based on a [Trinamic TMC 2100](http://www.trinamic.com/products/integrated-circuits/stepper-power-driver/tmc2100) or [Trinamic TMC 2130](http://www.trinamic.com/products/integrated-circuits/stepper-power-driver/tmc2130).
The driver boards are hardware compatible with [StepStick](http://reprap.org/wiki/StepStick) and [Pololu A4988](https://www.pololu.com/product/1182).

[![SilentStepStick](https://github.com/watterott/SilentStepStick/raw/master/hardware/SilentStepStick_v12.jpg)](http://www.watterott.com/en/SilentStepStick)


## Shop
* Trinamic **TMC2100** based drivers (CFG pins for configuration)
  * [TMC2100 SilentStepStick (3.3-5V)](http://www.watterott.com/en/SilentStepStick)
  * [TMC2100 SilentStepStick (3.3-5V) with soldered Pin Headers](http://www.watterott.com/en/SilentStepStick-with-Pins)
* Trinamic **TMC2130** based drivers (SPI for configuration)
  * [TMC2130 SilentStepStick (3.3-5V)](http://www.watterott.com/en/SilentStepStick-TMC2130)
  * [TMC2130 SilentStepStick (3.3-5V) with soldered Pin Headers](http://www.watterott.com/en/SilentStepStick-TMC2130-with-Pins)
* Accessories
  * [SilentStepStick Protector (with flyback diodes)](http://www.watterott.com/en/SilentStepStick-Protector)
  * [Suitable Heatsink 10x10mm](http://www.watterott.com/en/Pin-heatsink-square-ICK-S-10-x-10-x-125)
  * [Suitable Heatsink 10x6mm](http://www.watterott.com/en/Heatsink-for-DIL-IC-PLCC-und-SMD-10-x-6-mm)


## Features
* Hardware compatible with [StepStick](http://reprap.org/wiki/StepStick) and [Pololu A4988](https://www.pololu.com/product/1182)
* Trinamic TMC21x0 stepper motor driver
* Step/Dir interface with up to 16 microsteps and 256 microsteps interpolation
* Motor current: up to **1.2A RMS** continuously and 2.5A short time peak current per coil
* Motor voltage: **5.5...45V**
* **microPlyer** - microstep interpolator for increased smoothness of microstepping
* **stealthChop** - for quiet operation and smooth motion
* **spreadCycle** - highly dynamic motor control chopper
* Extra features of **TMC2130**:
  * SPI configuration interface (up to 4MHz)
  * up to 256 native microsteps (without interpolation)
  * **coolStep** - current control for energy savings
  * **stallGuard** - sensorless motor load detection
  * **dcStep** - load dependent speed control


## Hardware
* [Schematics/Layout + Guide](https://github.com/watterott/SilentStepStick/tree/master/hardware)
* [FAQ (Frequently Asked Questions)](https://github.com/watterott/SilentStepStick/blob/master/docu/FAQ.md)
* [Eagle CAD Part](https://github.com/watterott/Eagle-Libs)


## Reviews and Tests

* Review from Thomas Sanladerer:

  [![SilentStepStick/TMC2100 Review](http://img.youtube.com/vi/g6Bxoqr8QlY/0.jpg)](https://www.youtube.com/watch?v=g6Bxoqr8QlY)

  [![SilentStepStick/TMC2100 Review Update](http://img.youtube.com/vi/mYuZqx8xwTg/0.jpg)](https://www.youtube.com/watch?v=mYuZqx8xwTg)

* Review from Peter Recktenwald:

  [![SilentStepStick/TMC2100 Review](http://img.youtube.com/vi/P3ebhi-vZRY/0.jpg)](https://www.youtube.com/watch?v=P3ebhi-vZRY)

* Review from Georg Mill:

  [<img src="http://blog.georgmill.de/wp-content/uploads/2015/06/steppermotor_intro.jpg" width="400" height="225">](http://blog.georgmill.de/2015/06/18/schrittmotor-test-5-treiber-im-vergleich/)

* What is Trinamic stallGuard2 and coolStep:

  [![Trinamic stallGuard2 and coolStep](http://img.youtube.com/vi/Prw7wNa20Gk/0.jpg)](https://www.youtube.com/watch?v=Prw7wNa20Gk)

* Tests:
  * [Watterott (Stepper Motor)](https://www.youtube.com/watch?v=0l-HlntFYOY)
  * [Aleks (RepRap Prusa i3)](https://www.youtube.com/watch?v=33jQ0P7SMJA)
  * [Anthony (Delta Printer)](https://www.youtube.com/watch?v=CZOV0BdgSiU)
  * [Mario Lukas](https://www.youtube.com/watch?v=mJmg0iRHX8s)
  * Yusuke Sasaki: [TMC2100 steahlChop](https://www.youtube.com/watch?v=wrS7l46YJ_E), [TMC2100 spreadCycle](https://www.youtube.com/watch?v=391TY72wzPQ), [A4988](https://www.youtube.com/watch?v=iw6MRjzS6V4)
  * [MakerSpatz (Ultimaker)](https://www.youtube.com/watch?v=0jPbzB7XtWg)
  * [Aitor Esteve Alvarado (Ninja Prusa i3)](https://www.youtube.com/watch?v=c_TCVirnKJ0)
  * [Artur Wronowski (Delta Printer)](https://www.youtube.com/watch?v=hH2UkAmbfYs)
  * [3D Huynh (Felix 3D)](https://www.youtube.com/watch?v=EglFOpTXPtg)
  * [Easy 3D (Sparkcube)](https://www.youtube.com/watch?v=BxE_F8_Ec8M)
  * [WOLF HSW (linear drive)](https://www.youtube.com/watch?v=wjuAu0WYOPM)
  * Clarence Lee (ATOM Delta Printer): [TMC2100](https://www.youtube.com/watch?v=sBVNqFybUZI), [DRV8825](https://www.youtube.com/watch?v=tNufJnybsxg), [A4982](https://www.youtube.com/watch?v=r1noUt2UoO8)
  * Alex Tien (3DP Delta Printer): [TMC2100](https://www.youtube.com/watch?v=RcqnXXp4tPA), [A4988](https://www.youtube.com/watch?v=F2oB_NOLxHU)
  * swdjojo (Prusa i3): [TMC2100](https://www.youtube.com/watch?v=vBRNifmHaZE), [A4988](https://www.youtube.com/watch?v=TCgErVx93OA)
  * [Doc. Snuggles (Stepper Motor)](https://www.youtube.com/watch?v=gj6f6HSrHc4)
  * [Robert Sertic (Ultimaker)](https://www.youtube.com/watch?v=1wQJZb0gzoE)
  * [Emanuel Kant (Ultimaker)](https://www.youtube.com/watch?v=Y7CG43yf9zA)
  * [ghicione (EggBot)](https://www.youtube.com/watch?v=4FBAAQXnESU)
  * Edward Kuo: [E3D Cyclops Delta Printer](https://www.youtube.com/watch?v=iEYdrMH69oo), [TMC2100 water cooled](https://www.youtube.com/watch?v=vjNM9R0NZG0)
  * [Noah Ahmad Connor (Prusa i3)](https://www.youtube.com/watch?v=mNdl3s8TYmY)
  * [Sterillium (XYZ DaVinci)](https://www.youtube.com/watch?v=k-szP5wuplM)
  * [markg21405 (Delta Printer)](https://www.youtube.com/watch?v=tytL3KeIlLw)
  * [JJiG (MakerFarm Pegasus)](https://www.youtube.com/watch?v=9Rny6n1MCfI)
  * [René Jurack (Skimmy v3)](https://www.youtube.com/watch?v=qpl8v0k1_34)
