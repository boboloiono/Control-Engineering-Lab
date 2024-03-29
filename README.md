# Control-Engineering-Lab
This class will understand the application and physical significance of control engineering theory through practice by learning Matlab, Simulink, BLDC motor Lab, and implement LEGO Final Project
## Final report: Tracking Wheel Robot
[Video] https://youtu.be/_vlSjv4uhcM
<img width="1440" alt="截圖 2024-03-12 下午9 08 52" src="https://github.com/boboloiono/Control-Engineering-Lab/assets/62455939/329f17c4-24b0-46f1-8478-4b6f9233ab45">

### Program execution flow
Press touchSensor:
Continuously use getColorReflected(S3) to read the reflection value
It is executed in two situations:
- If the reflection value is less than a range value, it means that the car is currently on the black line and should go straight.
- If the reflection value is greater than a threshold value, it means that the car is currently off the track and begins to correct the route:
  - Back up until the car receives the black line signal
  - Turn 30 degrees to the right and record how many times the sensor receives the black line signal.
  - Turn left 30 degrees and return to straight
  - Turn left 30 degrees and record how many times the sensor receives the black line signal.
  - Turn right 30 degrees and return to straight
  - Finally, turn the car to a place where more black line signals are recorded, and you will be able to return to the track smoothly.

### Difficulties encountered and solutions
- Unable to negotiate right-angle corners smoothly
  - sol: Add the back function to the program
- The gyroscope is not accurate enough, and continuous small-angle adjustments can easily deviate from the track.
  - sol: turn a large angle at once
- After correcting the angle, you may continue to hit the wall.
  - sol: deflect one more angle to ensure the car deflects in the expected direction
 
# Improvement
- Try to escape the control of the gyroscope
- Use more aggressive acceleration strategies
