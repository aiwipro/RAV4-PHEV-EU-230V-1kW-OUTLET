## 2025 RAV4 PHEV (EU Spec) 150W to 1000W 230V Outlet Upgrade – Stock Look

The US version of the 2025 Toyota RAV4 PHEV/Prime has a 1500W 110V AC outlet in the rear cargo area for its higher trim versions.

The EU version of the 2025 Toyota RAV4 PHEV/Prime has a 150W 230V AC outlet in the rear cargo area for its higher trim versions.

150W is barely useful, as even some laptops may require more power than this. Though not confirmed, some sources claim this limitation is due to EU regulations.

In this project, we upgrade the maximum output power of the rear AC outlet in the EU version of the 2025 Toyota RAV4 PHEV to 1000W using a 12V inverter.

The build is 100% reversible and non-destructive. There should be no warranty issues, but as an extra precaution, all parts can be removed prior to sending the car for annual service.

The inverter will need a steady supply of fresh air when in use. Therefore, it is placed in the rear compartment intended for charging cables.

There are several options for which inverter to use. The Victron 12/1200 Inverter is an excellent choice, as it has a 12V trigger input for on/off. Due to cost constraints, this project uses a Renogy 1000W inverter instead.


## The Plan

The US version has its inverter connected to the high-voltage system. We will not touch this system, and instead connect our inverter to the starter battery—a regular 12V battery located in the rear cargo area.

The output power we can achieve is limited to the maximum current the internal system can supply when charging the starter battery. According to online sources, this limit is approximately 1250W. Charging is handled by an internal DC-DC converter, with current flowing from the high-voltage system to the low-voltage starter battery.

The stock 230V Schuko outlet will be reused in this project. However, it has very thin wires and a special connector to the car. We will simply use the socket and fit our own cable directly to the outlet’s pins. Since we won’t have regular 230V 16A household power connecting to the outlet, its internals appear more than capable of handling the very low currents for this project. The maximum current will be about 1000W ÷ 230V ≈ 4.4A.

Without modifications, the inverter will run regardless if the car is on or off. This is problematic, as it will drain the starter battery if not manually shut off. To automate power on/off for the inverter, the 12V cigarette lighter outlet next to the Schuko outlet will be used as a trigger. By default, both outlets have power when the car is in the READY state (turned on). Using an optocoupler or relay, we use the presence of 12V to trigger the inverter to turn on. When voltage drops to 0V (car turns off), the optocoupler/relay will switch the inverter off.

It is possible to make the on/off relay control the 12V high-current wiring directly, but it is preferable to use an inverter with a wired remote control feature. The Victron 12/1200 has a 12V trigger port, and the Renogy 12V 1000W inverter has a control board connected for on/off. This reduces the risk of failure in the high-current harness and can provide soft-start functionality (depending on the inverter).


## Parts List

- Renogy 1000W 12VDC → 230VAC Inverter

- 35mm² (included with the inverter) 500mm DC wiring with lugs

- 150A in-line fuse for 12VDC

- 3pcs 2.8mm crimp connectors for the Schuko outlet

- Wire and IEC60320 C14 receptacle for the Schuko outlet

- AC power cable (Inverter → IEC receptacle)

- Low-voltage wiring (PC fan wiring used in this build)

- Low-voltage connectors (PC fan wiring used in this build)

- Optocoupler / relay for 12V power-on detection

- RJ45-terminated low-voltage wiring (Ethernet cable used in this build)

- Electrical tape

- Heat shrink tubing

- Zip ties


## The Build

### 12VDC High-Current Cable

The inverter came with a set of 500mm long cables with pre-installed cable lugs.

The red cable is cut approximately 100mm from one end, and a 150A fuse is installed in-line.

The black cable is left unmodified.

![image1](images/1.jpeg "the red cable")


### 12VDC Low-Current Trigger Cable

By slightly disassembling the 12V power outlet, it is possible to attach low-voltage wiring with a connector—without soldering. The cable is secured to the plastic shell of the outlet using a zip tie.

![image2](images/2.jpeg "12V trigger")


### 230VAC Outlet Cable

A cable with an IEC60320 C14 receptacle is cut, and 2.8mm flat-pin connectors are crimped to the cable ends.

After adding insulating heat shrink to each connector, they are connected to the separate pins of the outlet. The cable is then secured to the outlet’s plastic shell with a zip tie.

![image3](images/3.jpeg "IEC w crimps")

![image4](images/4.jpeg "IEC w crimps and tubing")

![image5](images/5.jpeg "outlets assembled")


### 12VDC Low-Current Cable with Relay and RJ45

The Renogy inverter’s remote control board connects via an RJ45 connector. When the remote switch is in the "on" position, pins 3 and 5 have continuity. In the "off" position, continuity is broken.

Using an Ethernet cable, the inverter can be turned on by shorting the blue-white and blue-green wires.

At one end, the optocoupler/relay is connected to the 12V outlet cable with a polarity-protected connector. The cable connects to V, G, and trigger (two wires used). Depending on your setup, some relays turn on when the trigger is "low" and others when it is "high."

At the other end, the optocoupler/relay is connected to the Ethernet cable—in this case, white-blue and white-green to the relay pins.

![image6](images/6.jpeg "the relay")

![image7](images/7.jpeg "the relay, wrapped")


## Installation into the Car

1. Reinstall the plastic part with the modified 230V and 12V outlets into the car.

2. If possible, switch the in-line 150A fuse to “off” and connect the red high-current 12V cable to the car battery, ensuring the fuse is close to the battery terminal. Connect the other end to the inverter.

3. Connect the black high-current 12V cable to the car battery and the inverter.

4. Connect the 230VAC cable to the inverter and the IEC connector.

5. Connect the 12V trigger cable to the inverter and the custom outlet trigger connector.

![image8](images/8.jpeg "installed")

![image9](images/9.jpeg "plastic panels reinstalled")

![image10](images/10.jpeg "closed cargo lid")