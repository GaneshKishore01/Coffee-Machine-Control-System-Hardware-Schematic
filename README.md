# Coffee-Machine-Control-System-Hardware-Schematic
This repository contains the hardware schematic for a microcontroller-based Simple Coffee Machine.
![Image Alt](https://github.com/GaneshKishore01/Coffee-Machine-Control-System-Hardware-Schematic/blob/main/Schematic.jpeg)
The system automates dispensing coffee powder, milk powder, water flow, heating, and final output control using an integrated electronics board.

System Description

The controller manages all major functions of a powder-based coffee machine:

1. Powder Dispensing (Auger Feeders)

Two stepper motors drive auger feeders:

Coffee powder auger

Milk powder auger

Standard stepper drivers (A4988/DRV8825 type) are used.

Each driver receives STEP, DIR, and ENABLE signals from the Arduino.

Microstepping pins are available for dose calibration.

2. Water Pump Control

A 12V DC pump delivers cold water into the mixing chamber.

Pump is driven through a MOSFET with:

Flyback diode

Gate resistor

Gate pulldown

Pump can be controlled with PWM for adjustable flow rate.

3. Cartridge Heater Control

The heater warms all water used in the drink (single-heater design).

Driven using a protected logic-level MOSFET.

Supports on/off or PWM-based temperature control.

Includes diode and appropriate filtering components.

4. Final Solenoid Valve (J4 Connector)

A 12V solenoid valve is used to control beverage output.

Prevents dripping and only opens when drink is ready.

Controlled through a MOSFET output with diode protection.

5. Flow Sensor Integration

A turbine-type flow sensor measures the exact water volume.

Connected to an interrupt pin on the Arduino.

Provides pulse-based measurement for consistent recipes.

6. Limit Switch Input

Used for position detection, door sensing, or auger home position.

Pulled up to logic voltage.

Filter capacitor included for noise reduction.

7. User Interface

128×64 I2C OLED display for system information.

Status LEDs (heating, ready, error).

A push button for initiating a brew cycle.

Additional reset switch for restarting the controller.

8. Power System

12V main supply for pump, solenoid, heater, and motors.

Onboard 5V regulator powers the Arduino and logic components.

Reverse-polarity diode and decoupling capacitors included.

Ground connections for logic, motors, and power are unified.

Features

Dual-auger powder dispensing (coffee + milk).

Controlled water heating using cartridge heater.

Pump-based water delivery.

Final solenoid valve for controlled output.

Precise water metering using a flow sensor.

Real-time user interface on OLED display.

Expandable and Arduino-compatible hardware design.
