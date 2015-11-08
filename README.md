# raspberry-pi-robotics

# by Dmitriy Buslovich

This is OOP Python code used to run an autonomous robot built on Raspberry Pi and sonar

I have sucessfully built a robot, which runs using these scripts

What you will need:

- Raspberry Pi (any version)
- Robot base where everything will be mounted. I used a tracked chassis Tamiya 70108.
- Motor Driver Board: DRV 8833.
- Two Servos 
- Servo control board (I used Adafruit AI 815). 
- Sonar HC-SR04

The robot schematics are here: https://cloud.githubusercontent.com/assets/889838/11018099/8ee63026-856d-11e5-8c5a-98f11b9a7865.png
You can see how all the sensors, servos, and motors are connected

The algorithm for navigation is very basic at this point but you should have everything you need to optimize it. I am not currently using the tilt server but you can

You start the program by running main.py.
The script activates sonar, which takes 5 readings, removes outliars and returns a median value.
