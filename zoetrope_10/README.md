Project 10 - Zoetrope

Objective
- Build a motorized zoetrope whose speed is controlled by a potentiometer. Buttons are used to start/stop the motor and change its direction.

How it Works
- The potentiometer controls the motor speed by changing the PWM signal sent to the motor driver
- One switch toggles the motor ON and OFF, while the other reverses the motor's rotation by changing which control pin is HIGH or LOW

Key Concepts
- H-Bridge
	- A DC motor requires more current than an Arduino pin can provide
	- The H-bridge receives small control signals from the Arduino and uses them to control a larger power supply connected to the motor
	- By changing which side of the motor is connected to positive and negative voltage, the H-Bridge reverses the direction of current through the motor

- Potentiometer
	- A potentiometer is an analog input device.
	- Rotating the knob changes the voltage.
	- The Arduino reads values from 0–1023.
	- The reading is divided by 4 so it can be used with analogWrite():
		- motorSpeed = analogRead(potPin) / 4;
	- This converts the range to 0–255 for PWM.

- PWM Motor Speed Control
	- The enable pin receives a PWM signal.
		- 0 → Motor off
		- 255 → Maximum speed
	- Changing the duty cycle changes the average voltage supplied to the motor, which changes its speed.

- Toggle Logic
	- Pressing a switch changes the motor's state
	- the '!' is used to flip values
		- 0 → 1 and vice versa
	
Possible Improvements
- Add a display that shows the motor speed using an LCD
- Create speed presets where clicking a switch makes the motor go a specific speed