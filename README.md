# Control-Engineering-Lab
This class will understand the application and physical significance of control engineering theory through practice by learning Matlab, Simulink, BLDC motor Lab, and implement LEGO Final Project
## Final report: Tracking Wheel Robot
[Video] http://www.youtube.com/watch?v=OlEviMmKF68
![image](https://github.com/boboloiono/Control-Engineering-Lab/assets/62455939/2c856a61-81b8-479f-90f5-bff5a44385a2)

### Program execution flow
Press touchSensor:
Continuously use getColorReflected(S3) to read the reflection value
It is executed in two situations:
1. If the reflection value is less than a range value, it means that the car is currently on the black line and should go straight.
2. If the reflection value is greater than a threshold value, it means that the car is currently off the track and begins to correct the route:
  1. Back up until the car receives the black line signal
  2. Turn 30 degrees to the right and record how many times the sensor receives the black line signal.
  3. Turn left 30 degrees and return to straight
  4. Turn left 30 degrees and record how many times the sensor receives the black line signal.
  5. Turn right 30 degrees and return to straight
Finally, turn the car to a place where more black line signals are recorded, and you will be able to return to the track smoothly.

### Difficulties encountered and solutions
- Unable to negotiate right-angle corners smoothly
  - sol: Add the back function to the program
-The gyroscope is not accurate enough, and continuous small-angle adjustments can easily deviate from the track.
  - sol: turn a large angle at once
- After correcting the angle, you may continue to hit the wall.
  - sol: deflect one more angle to ensure the car deflects in the expected direction
 
# Improvement
- Try to escape the control of the gyroscope
- Use more aggressive acceleration strategies
