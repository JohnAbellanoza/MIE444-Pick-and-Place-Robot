# Autonomous Pick and Place Robot - MIE444 Mechatronics Principles

This is the final version of the python, MATLAB, and Arduino code my colleagues and I developed to autonomously control our robot "STEVE" during our 2023 Fall Semester at the University of Toronto. This code enabled the robot to operate its pick and place and navigation capabilities autonomously. 



## The Challenge

Our autonomous pick and place robot had to accomplish the following:

- Sense its surroundings and obstacles from onboard sensor data
- Localize itself within a pre-determined 4 ft x 8 ft maze
- Navigate to the loading zone while avoiding wall collisions
- Sense, pick up, and contain the load
- Navigate back to 1/4 specified drop off points and deliver the package

This was to be completed within a three month time period. To accomplish this, the robot had to meet the following milestones:

- Achieve obstacle avoidance by driving 20 ft in the maze without hitting any walls
- Achieve localization after driving a 5 ft distance in the maze while avoiding obstacles
- Localize itself in the maze, drive to the pickup point, acquire the load, and drop it off at the specified delivery point.

## Overview of the Main Control Code

The code uses a 2D histogram localization algorithm that runs on python and the MATLAB engine library. This was done to expedite development using a modified version of provided sample MATLAB code. This decision avoided headaches some teams experienced transferring the MATLAB algorithm and visualization over to Python

The code discretizes variable sensor readings from ultrasonic and time of flight sensors to determine if a wall exists around the robot in one of four cardinal directions. This data is fed into MATLAB where it then updates its probability matrix. 
The location of the robot via its index in the p-matrix is sent back to python. 
The robot then moves based on a series of if conditions that act on that locational data.
