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
