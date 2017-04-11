[![Gitter](https://badges.gitter.im/BCN3D/BCN3DSigma-Electronics.svg)](https://gitter.im/BCN3D/BCN3DSigma-Electronics?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

# BCN3D Electronics

This repository will hold all the information about the Electronics of the BCN3D Sigma.

As a declared Open Source organization, it's in our mission to release all the original design files to you to be able to learn, reuse and improve. Open Source not only means code, it also concerns hardware.

We've managed to design and manufacture our custom Electronics for the BCN3D Sigma in many ways thanks to the community and other Open Source Hardware projects.
BCN3D Electronics is a mashup between the [Ultimaker 2 Board](https://github.com/Ultimaker/Ultimaker2) , the [Megatronics v3.0](http://reprap.org/wiki/Megatronics_3.0) and some others...

## Design concept

The BCN3D Electronics is intended to be modular and custom fitted in our BCN3D Sigma 3D printer and that's why we made some design decisions.

1. Stepper drivers out of the Mainboard. As the drivers generate quite a lot of heat, we've moved them nearest as possible to the corresponding stepper motor. If one fails, you just have to replace a cheap stepper driver board. This way, we've managed to fit an entire electronics system without a fan.
2. FFC's everywhere. The BCN3D Sigma is an Independent Dual Extruder Printer so the Electronics supports 6  Axis of movement. Thats a lot of wires and wires takes some precious space. We decided to go with a Flat Flexible Cable solution that keeps things organized and it's faster to assemble.
3. 24VDC Power Supply. The performance improves as the whole Electronics run cooler while maintaining a very low voltage system.  
4. Full Color Resistive Touch Screen. The electronics is compatible with 4D Systems Displays out of the box. We think the user should interact with an intuitive interface to be able to use the printer easily even without previous experience in 3D printing.

## Boards

+ **Mainboard:** This board holds the microcontroller, the 5V switching power supply, the power outputs and the thermistor inputs. It has a USB interface for upgrading the firmware and communicating with the printer via serial port.
+ **Stepper Driver:** We carry the well-known DRV8825 stepper driver from Texas Instruments. It's able to supply plenty of power for all the types of stepper motors in the BCN3D Sigma.
+ **Extruder Board:** It's a simple interconnection board between the Mainboard and the components of the hotend assembly. With just one Flat Flexible Cable you the microcontroller has control over the hotend, the thermistor and endstop readings and the layer fan.
+ **Heated Bed:** As the platform size of the BCN3D Sigma is quite big, we've made a custom A4 size heated bed to achieve the performance required. It can heat up to 100ºC in about 6-8 minutes and keep that temperature for long period of times.
+ **SD Reader:** We've design our own SD Reader module with better signal integrity and better power supply requirements. This board has been designed entirely in [KiCAD Open Source software](http://kicad-pcb.org/). 


## Production

We strongly believe that using high quality components has an effect on the electronics performance as well as in the printer performance.

This is why we ensure components quality and control of the production process by designing and manufacturing in Barcelona. In this manner we iterate faster, reducing time to market.

Being in control of all the supply chain allows us to optimize designs and reduce costs.

## Contributing

If you own a BCN3D Sigma and electronics is your thing, feel free to post an [issue](https://github.com/BCN3D/BCN3D-Electronics/issues). We know this is still an 8-bit platform but we're working on optimizing it to the max and thinking in the next generation of 3D Printing Electronics. Always Open Source.

### License

Under the **LICENSE** folder you'll find all the information about the license. We've chosen CERN Open Hardware License and you must follow the guidelines as we had. All the documentation is available to you to study it, modify it and share it.
In addition, if modifications are made and distributed, it must be under the same licence conditions – this is the ‘persistent’ nature of the licence, which ensures that the whole community will continue benefiting from improvements, in the sense that everyone will in turn be able to make modifications to these improvements.
