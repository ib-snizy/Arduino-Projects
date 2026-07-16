Project 8 - Digital Hourglass

Objective
- create a timer that lights LEDs one at a time to simulate time passing

How it Works
- The Arduino uses 'millis()' to measure elapsed time without stopping the program
- Every set interval (3 sec), the next LED turns on

Key Concepts
- millis()
	- Returns the number of milliseconds since the Arduino started running
	- Allows for timing without using 'delay()' function
	- Since 'delay()' pauses the entire program, 'millis()' lets the Arduino continue checking other inputs while keeping track of time

- unsigned long
	- Can store larger numbers than 'int', but only positive values
	- We used it in this project because time can only be positive 

Possible Additions
- Make the LEDs blink after they have all been turned on
	- use 'digitalRead()' on all of the LED pins and check if they are all 'HIGH'
	- if so, make them all blink

Main Takeaway
- This project introduced non-blocking timing using millis(), which allows the Arduino to keep track of time while still running the rest of the program. I also learned how storing previous values, such as previousTime and prevSwitchState, allows the Arduino to measure elapsed time and detect changes in inputs, making programs more responsive and efficient than using delay().