Project 7 - Keyboard Instrument

Objective
- Create a keyboard instrument where different buttons produce different musical notes	

How it Works
- Switches are connected with different resistors to create different voltage levels
- The Arduino reads the voltage at analog pin A0 using 'analogRead()'
- Each button creates a different analog reading
- The Arduino compares the sensor reading using if and else statements and uses 'tone()' to play the desired frequency through the piezo

Key Concepts
- Analog Input
	- Allows Arduino to measure changing voltage values
	- analogRead() converts voltage into 10-bit ADC value
		- 0 → 1023
		- 0V → 0
		- 5V → 1023
	- Digital inputs only read:
		- HIGH (1)
		- LOW (0)

- Resistor Ladder
	- Resistors create different voltage levels depending on which switch is pressed
	- The Arduino do not directly know which switch is pressed, instead, it reads the voltage at A0 and determines the button based on the value
	- Button pressed → Voltage Changes → analogRead() value changes
	- Using and (&&) statements, we can create a range where a different note is played for the corresponding voltage being read at A0

- Arrays
	- Arrays allow multiple related values to be stored under a single variable
	- Values in an array are accessed using an index array[0]

Challenges
- Debugging the Resistor Ladder
	- Initially, multiple buttons produced the same analog readings
	- This meant that the Arduino could not distinguish between buttons
	- By using the Serial Monitor, I was able to see the actual voltage readings and identify that the resistor placement was incorrect
	- After fixing the placement, each button produced a different value

- Adjusting ranges
	- Analog readings can change due to electrical noise and resistor tolerance
	- So, instead of checking for a single value, I used my serial monitor to see the general voltage range of each button
	- Using this, I adjusted my if statements to ensure that a noise would be produced the whole time a button is pressed

Main Takeaway
 - The project showed how Arduino can use analog inputs to identify different states. Instead of a button only being ON or OFF, different resistor valyes allow multiple buttons to create different voltage levels. This introduced the idea of using sensors and voltage signals as inputs, which is important for real world electronics like control systems and interfaces.