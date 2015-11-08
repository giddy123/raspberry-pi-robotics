# raspberry-pi-robotics

# by Dmitriy Buslovich

This is OOP Python code used to run an autonomous robot built on Raspberry Pi and sonar

I have sucessfully built a robot, which runs using these scripts

What you will need:

- Raspberry Pi (any version)
- Robot base where everything will be mounted. I used a tracked chassis Tamiya 70108. You may need to buy a gearbox that can have the left wheel and the right wheel rotate independently; otherwise your robot will not be able to make turns :)
- Motor Driver Board: DRV 8833.
- Two Servos. You can forgo the servos altogether and mount the sonar in a fixed position.
- Servo control board (I used Adafruit AI 815). If you are not using servos, then you obviously don't this board.
- Sonar HC-SR04
- 1k resistor for the sonar. See schematics for details.
- Three batteries: one for the Raspberry Pi (I am using a cell phone battery), one for the motors, and one for the servos. Make sure you are sending the correct voltage to the corresponding components. 
- Pan/tilt mechanism for the servos. I built one myself but there are many ready-to-go options online. 

The robot schematics are here: https://cloud.githubusercontent.com/assets/889838/11018099/8ee63026-856d-11e5-8c5a-98f11b9a7865.png
You can see how all the sensors, servos, and motors are connected

The algorithm for navigation is very basic at this point but you should have everything you need to optimize it. I am not currently using the tilt server but you can

You start the program by running main.py.
The robot turns the sonar to the left, to the right, and center. It takes 5 readings, removes outliars and returns a median value. It then turns in the direction where the value is the largest (farthest distance) and starts moving. The robot takes readings while in motion. If it encounters an obstacle, it stops and "looks" around again to figure out where to go next.
