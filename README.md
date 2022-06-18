# Control an LED via Cloud
### An introduction to NodeMCU - ESP8366 and a basic program to control an LED via the cloud.  
<br/>

***Introduction to NodeMCU - ESP8266 :***  
ESP8266 is a low-cost WiFi-enabled microcontroller chip, produced by [Espressif Systems](https://www.espressif.com/en). [NodeMCU](https://www.nodemcu.com/index_en.html) is the development kit for the ESP8266 microcontroller. It is a low-cost open source IoT platform. It is one of the easiest ways to discover the capabilities of WiFi enabled chips. 

<p align="center">
  <kbd>
    <img src="https://user-images.githubusercontent.com/77038120/174355234-1163a826-3dce-46cc-9bbf-b0d49f26d100.png">
  </kbd>
</p>

As the chip comes with WiFi on board, it opens up many possibilities that are not generally possible with other beginner-friendly microcontroller development kits like Arduino Uno. One of the important feature of NodeMCU is its ability to connect to Cloud Technologies, such as [Arduino IoT Cloud](https://cloud.arduino.cc), [Blynk IoT Cloud](https://blynk.io/), [ThingSpeak IoT Cloud](https://thingspeak.com/), etc.

***About Arduino IoT Cloud :***  
It is an online cloud platform, that makes it easy for us to collect data, monitor and control devices over the air. It's UI is simple, and easy to navigate and explore. Arduino Cloud has a free plan with limitations, along with some paid subscriptions that give more contorl over the data. It provides us with both a web app for desktop, as well as a mobile application for both iOS and Android. For this project, we are using Arduino Cloud along with NodeMCU to control the LED.  
<br/>

***Project Overview :***  
A simple project that demonstrates the basics of Arduino Cloud in integration with NodeMCU. A simple "On-Off" switch is designed in the Arduino Cloud dashboard to control the working of the LED.  

***Required Components :***  
- NodeMCU - ESP8266
- LED (any colour)
- Resistor (1k Ohm)
- Breadboard
- Jumper Wires
<br/>  

***Software Requirements :***
- Arduino IDE ([Download](https://www.arduino.cc/en/software))
- Arduino IoT Cloud ([Register](https://cloud.arduino.cc))
- Drivers for NodeMCU ([Download](https://github.com/nodemcu/nodemcu-devkit/tree/master/Drivers))
<br/>  

***Connections :***  
Use a breadboard for connections.
- Connect the D0 pin of the NodeMCU with Anode of LED via a resistor.
- Cathode of the LED is connected to ground.
<br/>

### Setting up the Arduino Cloud Environment  
***Adding a new Device :***
- Hover over to Arduino Cloud website ([Click Here](https://cloud.arduino.cc)) and register for an account.
- Once registered, go to the "Devices" section and add a new device.
- Select third-party device and ESP8266. After that, select the model of NodeMCU you have from the drop down menu. Click on continue.
- Give it an appropirate name and click on continue. 
- A device ID and a secret key are generated. Save them safely, as we will need them later in the process.
<br/>

***Creating a Thing :***  
A thing is the main project area where the code is written. It associates the device we created in the previous step with the code. Follow the below steps to create a new thing.  
- Once a devie is created, head over to the "Things" section and create a new thing.
- You can rename the thing, and then add some variables that are required. 
- Now, in the "Associated Device" section, click on Select Device.
- In the new window, select the device previously created to associate with the thing.
- Just below is a Network sub-section. Select "Configure" option and enter your WiFi details in the provided space.
- Also, enter the secret key that was generated previously. 

Note that for each variable that is added into the thing, there is a function that is created in the "Sketch" part that is associated with the variable. This variable is what syncs the data between the cloud and the devices.

***Coding the NodeMCU :***  
Most of the code is pre-written by the Arduino Cloud, and we just need to do some changes inside the functions. If you selected the variable to be of "On Change" type, then the function corresponding to the variable will get executed everytime the value of the variable changes.

#### Full details will be updated soon. Please standby!
