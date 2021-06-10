# 1) Wake Word Detection
The main objective of the project is to trigger a task when the wake word is said. Here we are going to control the state of an led using the wake words "yes" for 'on' and "no" for 
'off' , using tinyml on esp32.

## Required components
* Microphone
* LEDs(there are inbuilt LEDs)
* esp32

## Parts of the project:
![Screenshot 2021-06-10 074602](https://user-images.githubusercontent.com/75152245/121454210-06ce0180-c9c0-11eb-8c18-c8160d8ccc64.jpg)

### Main Loop:
The program runs on a continous loop which listens for the words and processes the input and gives the output for the corresponding input.
### Audio Provider:
The audio provider captures the raw audio from the microphone and sends it to the feature provider.
### Feature Provider:
The feature provider converts the raw audio input into a spectrogram which the model can process to identify the corresponding wake word.
### Tensorflow Lite Interpreter:
The Tensoflow Lite Interpreter runs the model in the microcontroller, which identifies the wake word.
### Model :
A Tensorflow deep neural network model is created, which is trained on speech datasets ,and improved to a promising accuracy.
Then the Tensorflow model is converted into a tensorflow lite model using a Tensorflow Lite Converter, the model is converted from a Keras into a FlatBuffer format which consumes very
less space in the disk.
Then the model is coverted into a C source file which can be run by the microcontroller.
### Command Regoniser:
As the inference is run multiple times a second, it regonises on an average whether the word is heard or not.
### Command Responder:
If a command is heard, depending on the wake word heard, its corresponding task is triggered (here the task is to light an led, if the heard word is yes it makes the led go on if 
it is no it makes the led go off.

# 2) LIDAR Based Self Driving Car
 The objective of this project is to make a miniature car which uses LIDAR to detect the obstacles and avoid them while travelling. 
 LIDAR is a method which is used to determine the range of distance of the obstacles, by emiting laser on the target object and measuring the time for receiving the reflected ray.
 
 ## Required Components:
 * LiDAR 
 * Microcontroller
 * Transistors
 * Resistors
 * LEDs
 * DC motors
 * Servo motors
 * Motor driver
 * cable and connectors
 * Breadboard
 * Pushbuttons
 
 ## Project demonstration:
 
![ezgif com-gif-maker](https://user-images.githubusercontent.com/75152245/121466982-e9a42d80-c9d5-11eb-987f-8493998c5e00.gif)

## Block Diagram:
![Screenshot 2021-06-10 102503](https://user-images.githubusercontent.com/75152245/121467110-296b1500-c9d6-11eb-8e49-92c63e695239.jpg)

## Description:
The car moves with the constant speed using the 4 DC motors connected to the motor driver.
The LiDAR provides the information of range of the obstacles around the car to the micro-contorller.
The micro-controller processes the given data and decides on the direction which has low obstacles and controls the servo motors which are attached to the axle of the car wheels and changes direction when required.
This system makes the car detect the obstacles and avoid them while  course of travelling.

## Improvements from my side:
I would like to make the car
* to decide the shortest distance available between the start point and the target.
* to control the speeds of the car when required. 

# 3) Person Detection:
The objective of this project is to switch on a LED if a person is detected in the image.

## Application Architecture:
* Obtain an input image.
* Preprocess the image to obtain features and suitable format to be feed into the model.
* Run the model with the input features and obtain an output.
* Post processing the obtained output.
* Turning the LED on and off for respectively obtained output.

## Required Components:
* Camera Module
* LEDs
* Microcontroller

## Block Representation:
![Screenshot 2021-06-10 110200](https://user-images.githubusercontent.com/75152245/121470107-5110ac00-c9db-11eb-99db-8f6c85748e3d.jpg)

## Description:
Here we will see how the different components in the block diagram come together to give the system.

### Main loop:
The program runs through a continous loop, which makes inferences every few seconds.
### Image Provider:
This component captures the image from the camera and writes to the input tensor.
### TensorflowLite Interpreter:
The interpreter takes the input tensor and runs it in the model.
### Model:
The model is included as a data array and run by the interpreter. We will create a Convolutional Neural Net using the Tensorflow's Keras API and train it on datasets then optimising the neural net to obtain a desired accuracy. Then conerting the model to a Tensorflowlite model using the tensorflowlite converter.
### Detection Responder:
The detection responder takes the output from the model and triggers the corresponding task here it is to on the LED when person is detected.

# 4)







 