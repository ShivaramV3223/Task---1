# Improving the Projects
In this file we will see some improvements in 2 projects chosen from the Mini_Task_1 file.

## The Projects:
* Wake word detection
* Obstacle avoiding self driving car

## Wake word detection

### Ideation an planning:
Here our main aim is to detect whether a specific word has been said or not. This majorly used in todays virtual assitant, in which a wake word is detected it triggers the device to listen and take audio inputs and process  them using NLP and give us corresponding output.

### Pipeline:
|Part of Pipeline|Feasibility|Advantages|Disadvantages|
|----------------|:---------:|:--------:|:------------|
|Microphone      |easy operation|widely available, cheap, easy operation, no battery required| reduced performance at higher frequencies|
|Micro-controller|cheap and easily programmable|reusable,straightforward,many tasks can be handled at the same time|limited memory and computation|
|Deep learning model|little hard to understand|brings its own features, high efficiency compared to other methods|requires lots of data, expensive to train complex models|

### Choosing a pipeline:
As we use a single microphone to detect the wake word, it might be difficult to separate the human voice if there is background noise. To overcome this we can use more microphone to precisely get the human voice or may use another algorithm for separation of voice from the background noise. We can also make our training datasets to cover the cancelation of effect of background noise.


## Obstacle avoiding self driving car
### Ideation and planning:
In this project we are aiming to create a car which avoids obstacles on its own and take a direction which as a less obstacles.

### Pipeline:
|Part of Pipeline|Feasibility|Advantages|Disadvantages|
|----------------|:---------:|:--------:|:------------|
|LiDAR|Very expensive|High accuracy, High speed performance, provides a 3D map|Expensive, limited range in low light, collects too many data|
|micro-controller|easy to work with for people who know little bit of coding|reusable, straightforward|limited by computations and memory|
|Servo motors|helpul with controlled rotations| Highly reliable, high efficiency, quiet operation, smooth running|slightly higher cost|
|DC motors|cheap and easily available| High starting torque, variable speeds with voltage|needs motor driver to increase the voltage|

### Choosing a Pipeline:
In this project the efficiency is really high because of LIDAR, on the other hand its highly expensive. To make it cheaper and easier to use we may substitute the LiDAR sensor with Ultrasonic sensors. By increasing the number of Ultrasonic sensor might increase the accuracy of object detection. We could program such that the car decides the less obstacle path from readings of different sensors at different positions.

