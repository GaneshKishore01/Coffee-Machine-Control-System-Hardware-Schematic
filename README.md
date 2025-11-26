⭐ Overview

This system automates:

Coffee powder dispensing

Milk powder dispensing

Water pumping

Cartridge water heating

Final solenoid valve output

Flow metering

User interface (OLED + LEDs + button)

Everything is controlled using a microcontroller-based board compatible with Arduino.

🔧 System Description

The control board manages all major functions inside a powder-based coffee machine.

1. Powder Dispensing (Auger Feeders)

Two stepper motors are used to drive auger feeders:

Coffee powder auger

Milk powder auger

Stepper drivers (A4988/DRV8825 type) include:

STEP, DIR, ENABLE inputs

Adjustable microstepping

Current control (Vref)

This allows precise, consistent powder dosing.

2. Water Pump Control

A 12V DC pump pushes cold water into the mixing chamber.

Pump driver includes:

MOSFET control

Flyback diode

Gate resistor

Gate pulldown

Flow can be controlled using PWM for calibrated dispensing.

3. Cartridge Heater Control

A single cartridge heater warms all water before dispensing.

Heater control features:

Logic-level MOSFET

On/off or PWM-based control

Flyback diode and filtering

Supports PID or temperature-based heating logic (firmware)

4. Final Solenoid Valve (J4)

A 12V solenoid valve controls the final beverage output.

Opens only when drink is ready

Prevents dripping

MOSFET-driven with diode protection

5. Flow Sensor Integration

A turbine-based flow sensor measures the exact water volume.

Connected to an Arduino interrupt pin

Pulse counting ensures accurate recipes

Can be calibrated to ml/pulse

6. Limit Switch Input

Used for:

Door/cover sensing

Auger feeder home detection

System safety

Includes pull-up and filtering for reliable operation.

7. User Interface

128×64 I²C OLED display

Status LEDs: heating, ready, error

Brew/start push button

Reset switch

Provides real-time machine status and control.

8. Power System

12V main input for pump, heater, solenoid, motors

Onboard 5V regulator for logic and Arduino

Reverse-polarity protection

Decoupling capacitors for all subsystems

Unified GND across logic and power

🚀 Features

Dual auger system (coffee + milk powder)

Controlled water heating using cartridge heater

Pump-driven water flow

Final solenoid valve output

Accurate water metering via flow sensor

OLED-based UI

Arduino-compatible hardware design

Modular, reliable, and easy to integrate
