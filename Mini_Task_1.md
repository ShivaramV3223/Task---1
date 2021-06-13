# 1) Wake Word Detection
The main objective of the project is to trigger a task when the wake word is said. Here we are going to control the state of an led using the wake words "yes" for 'on' and "no" for 
'off' , using tinyml on micro-controller.

## Required components
* Microphone
* LEDs(there are inbuilt LEDs)
* micro-controller

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

# 2) Obstacle based Self Driving Car
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

# 4) Dual Axis Solar Panel

## Objective:
To maximise the efficiency of solar panels by moving them and alligning them in the direction of maximum sunlight. 
It also shows the humidity and temperature in the LCD display

## Required Components:
* Solar Panel
* Micro-controller
* DC Motor
* Humidity sensor
* Photo resistors
* Resistors
* Transistors
* Servo motor
* Temperature sensor
* Rain sensor
* Cable and connectors
* LEDs

## Demonstrations:
![ezgif com-gif-maker](https://user-images.githubusercontent.com/75152245/121475085-9d131f00-c9e2-11eb-9e20-1db13e3f4299.gif)

## Block Diagram:
![Screenshot 2021-06-10 122240](https://user-images.githubusercontent.com/75152245/121481994-4dd0ec80-c9ea-11eb-829c-d654bbed1075.jpg)


## Description:
The photoresistors are placed at the corners of the solar panel to detect the amount of sunlight that falls on the panel and sends the data to the micro-controller.
The micro-controller then processes the data and uses the servo motors and stepper motors to allign in a direction that maximises the amount of  sunlight that falls on the panel.
In addition to this temperature and humidity sensors are connected to the micro-controller, which sends information to the micro-controller.
The micro-controller displays the values in the LCD display.

# 5) Smartphone connected door lock system
The objective of this project is to control the door lock of the house with a mobile app.

## Required components:
* Raspberry pi
* High Torque Servo Tower pro MG995R
* Jumper wires
* LED
* Spark Fun Pushbutton

## Demonstration:

![ezgif com-gif-maker](https://user-images.githubusercontent.com/75152245/121805196-c55f7f80-cc67-11eb-8665-64852a3f490b.gif)



## Description:
The door lock is first connected with the high torque servo motor, which moves the lock when desired.
The servo is connected to the Raspberry Pi board along with the an LED to show whether its locked or not.
The Raspberry Pi has a builtin WIFI which is linked to the smartphone through a software named 'Blynk'.
Multiple smart phones can be linked to the board through the software.
Using the app if  you press the unlock button, it transmits the signal to the Raspberry Pi which then operates the Servo to unlock the door.

# 6) IOT based Irrigation System
We are building an IOT system which detects the soil moisture and drives an airpump which pumps water to the plants.

## Required Components:
* Microcontroller
* Aquzrium Air Pump
* Container for storing water
* DF robot soil moisture sensor

## Demonstration:
![WhatsApp Video 2021-06-13 at 06 26 00](https://user-images.githubusercontent.com/75152245/121792279-6f132200-cc10-11eb-9466-572f8a95ca02.gif)

## Description:
The soil moisture sensor is the core part of this project. The soil moisture sensor sends information about the soil moisture to the micro-controller.
The micro-controller processes the information and finds whether the moisture level is less then the recommened level. If it is so then it turns on the aquarium air pump, which is attached to the reservoir. As the air pump blows air inside the reservoir the water is pushed outside through the other end.
The water flow continues untill the moisture level reaches the required level.

# 7) IOT Motion Controlled Servo
The objective is to  mimic the hand movements by a servo motors. Lets dive deep into this.

## Required components:
* Raspberry Pi
* Leap motion controller
* 5V power supply
* I2C enabled PWM driver
* 4 Micro servo motors
* 4 Micro servo mounts
* LEDs and resistors
* Hook wires

## Demonstration:



![ezgif com-gif-maker](https://user-images.githubusercontent.com/75152245/121793624-91ac3780-cc1e-11eb-9a4b-29bf0ed1083f.gif)


## Block Diagram:
![Screenshot 2021-06-13 071221](https://user-images.githubusercontent.com/75152245/121792784-bac8ca00-cc16-11eb-9a89-b6a8ea593cc1.jpg)

## Description:
The computer with the Leap motion controller is setup to publish data to the internet. The Raspberry Pi receives the data from the internet.
Here Pubnub is used as communication layer between the computer and Raspberry Pi. Raspberry Pi , from the received data talks to the other parts through I2C bus to accomplish the task. The ATMega328p matrix driver circuit controls the matrix of RBG matrix. The servo  motor driver receives information through I2C and controlls the 4 servos.

# 8) Arduino Data Glasses
This project aims at creating a device which mounts on the glass, which provides ease of knowing informations around us without turning around.

## Required Components:
* Arduino micro
* Mirror
* Bluetooth module
* Charging circuit
* micro oled display
* LiPo battery
* acrlyic plano convex lens

## Demonstration:
![ezgif com-gif-maker](https://user-images.githubusercontent.com/75152245/121793582-1c406700-cc1e-11eb-831b-ddb43b96b2cc.gif)

## Description:
There may be works in which we have to look to a device often from the workplace,data glasses solve this issue. You can veiw the details you need infornt of your eyes without moving to a particular place. The Arduino micro in the data glass collects information from the bluetooth module and manipulates it. After manipulation it displays it through the oled display. The image from the oled gets reflected by the mirror placed and it passes through the planoconvex lens and after which it reaches the reflector where it gets reflected to the eye. The reflected ray makes an virtual image at the reflector.

# 9) Wifi controlled Robotic Arm:
The objective in this project is to build a arm which can hold and lift things by instructions through wifi.

## Required components:
* Servo motors(9)
* Raspberry Pi(built in WIFI)
* acrylic sheets
* fixings

## Image:
![Screenshot 2021-06-13 084358](https://user-images.githubusercontent.com/75152245/121794125-8a3b5d00-cc23-11eb-9b93-5eb9c1b58881.jpg)


## Circuit Diagram:
![Screenshot 2021-06-13 083907](https://user-images.githubusercontent.com/75152245/121794060-db971c80-cc22-11eb-9954-138c86d92997.jpg)

## Description:
The structure of the arm is built from the acrlyic sheets. The servos are mounted at the joints so that we could move the parts of the arm. Through board and mobile are connected through the Blynk software through which, we can send the instructions like to turn right or leftor pick.

# 10) Quadruped Robot
The objective is to build a 4 legged dynamic robot which walks like four legged animals and responds to the instructions provided.

## Required components:
* Micro-controllers(one acts as brain and the other one for writing signals)
* IMU sensor
* Servo motors
* bulk converter
* Batteries for power supply
* controller

## Image:
![Screenshot 2021-06-13 091625](https://user-images.githubusercontent.com/75152245/121794843-36cc0d80-cc29-11eb-9882-4aef55075ef6.jpg)
## Demonstration:

![ezgif com-gif-maker](https://user-images.githubusercontent.com/75152245/121794979-6891a400-cc2a-11eb-83f6-c247407c5cb5.gif)

## Parts of the project:
![Screenshot 2021-06-13 085128](https://user-images.githubusercontent.com/75152245/121795052-abec1280-cc2a-11eb-9a5d-7727191ff4db.jpg)

## Description:
As mentioned there are two micro-controllers, one acts as the brain for the quadruped bot and the other one acts as the mediator between other parts and the brain. Here we are controlling the bot through a game controller so we require WIFI/ Bluetooth for the brain micro-controller. The datas from the IMU sensor are collected which is used to maintain the stability of the quadruped bot. There are 3 servo motors in each leg which helps in the motion of the quadruped. According to information from the controller and the IMU sensor the brain as been programmed to take decision and sends the instructions to the second micro-controller which in turn sends  instructions to the servos which causes the required / desired movement.

# 11) Inspector Bot
The objective is to build a bot which moves and captures images for inspecting dark areas where we can't go and inspect.

## Required components:
* Micro-controller (with in built WIFI)
* Camera modules
* LEDs
* resistors
* gearhead motors
* Wheels
* mini usb camera
* motor drivers

## Image:
![Screenshot 2021-06-13 100357](https://user-images.githubusercontent.com/75152245/121795642-4569f300-cc30-11eb-88be-7d067ae5cfbc.jpg)

## Description:
We are building a car like setup which is controlled by a game controller. Camera modules are attached to the body which provides us the information about what is around or bot.
The micro-controller receives information from the controller and makes the bot move in the desired way. The input from the camera module is transmitted to the user through the micro-controller.

# 12) Hand Gesture Controller
This project aims at controlling applications from a distance using the hand gestures. Lets see how it works.

## Required components:
* nRF24L01 Transceiver Module.
* ADXL335 Accelerometer.
* Arduino Pro Mini.

## Demonstration:
![ezgif com-gif-maker](https://user-images.githubusercontent.com/75152245/121796614-0c358100-cc38-11eb-8534-4e78a3075d50.gif)

## Description:
The nRF24L01 Transceiver module allows two or more Arduino board to communicate with each other wirelessly. A address is created for the nRF24L01 modules to communicate with each other. The important component is the 3 axis accelerometer, which calculates the static acceleration due to gravity while tilting the hand. The Arduino Pro mini acts as the master device which receives signals from the accelerometer and sends it to the transceiver module. The transceiver module sends the information to appilication which as to be controlled by the hand gestures. The application works by comparing the values of accelerometer with the min and max value for an action.

# 13) Motion Detection with Photo capture
The objective of the project is to capture photos with the camera module when a motion is detected.

## Required components:
* Raspberry Pi
* Jumper wires
* breadboard
* Camera module
* Pushbutton
* HS-SR501 PIR Motion sensor

## Circuit Diagram(Excluding Camera module):
![Screenshot 2021-06-13 150745](https://user-images.githubusercontent.com/75152245/121802306-364b6b00-cc59-11eb-802e-71f1eafff905.jpg)



## Description:
In this project motion sensor plays the major role. When the motion sensor detects a motion , it sends the information to the Raspberry Pi controller. The controller triggers the camera module to take an image and send it to the user.

# 14) Auto Targeting nerf turret
The objective is to create a nerf turret which locates a target and shoots them. Here target is provided by a red laser.

## Required components:
* Micro-controller (with bluetooth/ WIFI inbuilt)
* nerf gun setup
* servo motors
* camera module

## Demonstration:
![ezgif com-gif-maker](https://user-images.githubusercontent.com/75152245/121803596-0a7fb380-cc60-11eb-9426-dabb6f85a176.gif)

## Description:
The camera module provides the input as image to the micro-controller. The micro-controller processes the image and follows a red laser dot by computer vision. The target is given by the laser dot. If it coincides with the aim of the turret then it shoots automatically. The micro-controller moves the aim and camera with servo motors accordingly it follows the laser dot.

# 15) Mind controlled drone
The objective is to fly a drone which is purely controlled by mind.

## Required components:
* Micro-controller
* Mindwave neuralsky
* Mini racing drone
* Capacitors
* Resistors
* Jumper wires

## Demonstration:
![ezgif com-gif-maker](https://user-images.githubusercontent.com/75152245/121804200-d22da480-cc62-11eb-963a-b15cfa5e1d79.gif)

## Description:
In this project mindwave neuralsky plays the important role. It helps to connect the drone with the mind. The neuralsky takes mindwaves as input and converts into an API which can be connected to the drone through code.





#                                                              THE END























 
