Project 6 - Light Theremin

Objective
- Create a light-controlled instrument that changes pitch depending on the amount of light detected by a photoresistor.

How it Works
- Photoresistor detects changes in light intensity by changing its resistance
- Arduino reads the sensor value using 'analogRead()' and converts the reading into a frequency value
- the Arduino uses 'tone()' to generate different pitches through the piezo\
- more light/different sensor readings → different frequency → different sound

Key Concepts
- Analog Sensors
	- photoresistors output a changing voltage depending on light level
	- Arduino converts voltage into 10-bit ADC value from 0-1023
	- Higher/Lower readings can be mapped into useful ranges

- Mapping Values
	- Sensor values usually do not match the range needed for output
	- use 'map()' to convert sensor readings into frequencies

- Tone function
	- 'tone()' creates a square wave signal that drives the buzzer
	- the frequency value controls the pitch
	- higher frequency = higher pitch

Challenges
- Understanding pinMode()
	At first i did not understand why 'pinMode(ledPin, OUTPUT);' was needed.

	I learned that 'pinMode()' tells the Arduino how a pin will be used
		- 'INPUT' → Arduino reads info from a component (ex. sensor)
		- 'OUTPUT' → Arduino sends a signal to control component (ex. LED/Piezo)
	For this project, pinMode() is set as output because the Arduino needs to send signals to control the piezo

- Understanding map()
	I did not understand why 'map()' needed five values	

	The five inputs represent:
	1. The value being converted
	2. The minimum value of the original range
	3. The maximum value of the original range
	4. The minimum value of the new range
	5. The maximum value of the new range

	map(value, fromLow, fromHigh, toLow, toHigh)

Main Takeaway
- This project showed how sensors can be used as inputs to control outputs. The Arduino reads environmental data (light) and converts it into a useful output (sound).
	
