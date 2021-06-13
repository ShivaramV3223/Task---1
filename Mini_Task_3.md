# Debugging Projects:

## Wake word detection

### Hardware errors:
If the project doesn't work, we have to check whether there are any loose connections whithin the project. If that doesn't help,  check whether each particular component works.
As for this project the main hardware ingredients we need are microphone, micro-controller, LEDs, resistor for the LEDs. It easier to debug for hardware errors. If we use micro-controllers with in-built microphone and leds, Hardware errors less likely to happen. If it happens, it would be because of the board.

### Software errors:
In this project, the main part is programming a model for detecting the wake word. Our first aim is too create a model on PC and optimise it untill we get a promising accuracy.
The model can be optimised by tuning the hyperparameters. To not get stuck at plot the graphs of loss of both training and test datasets. We have look whether the graph reduces for increasing number of iterations. If the model does performances super in the training set more than the validation set, then we might encounter the problem of overfitting which can be avoided by reducing the size of neural nets and using regularistaions. On the other case we might encounter underfitting , where the model was not able to capture the pattern behind correctly, this might be improved by increasing the size of neural nets.

As we are implementing ML on micro-controllers, we need to take care of the size of neural nets with capturing the data more precisely. As increaing the size of nets may increase the memory required.

## Obstacle avoiding self driving car

### Hardware errors:
The first basic debugging to check whether the components work correctly and check whether the circuit is made correctly. Check which part of the car is not working properly, for example, if the car doesn't move there might be trouble in motors, like that check for a particular hardware which is not working well and debug that component.

### Software errors:
In this project, firstly we have to check whether the limits for take a diversion have been correctly implemented or not. If the car does not avoid the obstacles while experimenting we have to check whether the information from the LIDAR sensor is correctly interpreted by the micro-controller or not. If the moving parts cause a problem, check whether the motors are taking the right direction of spin when the LIDAR detects an obstacle or not. This project can be broken down to detecting and moving parts of the car. Finding the problem and debugging these separately will make it faster and easier.
