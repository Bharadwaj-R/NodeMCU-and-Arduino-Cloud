# NodeMCU and Arduino Cloud
### An introduction to NodeMCU - ESP8266 and Arduino Cloud 
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
Arduino Cloud is an online cloud platform, that makes it easy for us to collect data, monitor and control devices over the air. It's UI is simple, and easy to navigate and explore. Arduino Cloud has a free plan with limitations, along with some paid subscriptions that give more contorl over the data. It provides us with both a web app for desktop, as well as a mobile application for both iOS and Android.  

<p align="center">
  <kbd>
    <img src="https://user-images.githubusercontent.com/77038120/174824422-29e21c5a-0a78-4424-ac6a-cf206aeb0d26.png">
  </kbd>
</p>
<br/>

***Getting Started :***  
We will learn the basics of NodeMCU Programming and it's integration with Arduino Cloud.

***Software Requirements :***
- Arduino IDE ([Download](https://www.arduino.cc/en/software))
- Arduino IoT Cloud ([Register](https://cloud.arduino.cc))
- Drivers for NodeMCU ([Download](https://github.com/nodemcu/nodemcu-devkit/tree/master/Drivers))
- Arduino Create Agent ([Download](https://support.arduino.cc/hc/en-us/articles/360014869820-Install-the-Arduino-Create-Agent))
<br/>

### Setting up the Arduino Cloud Environment  
***Adding a new Device :***
- Go to Arduino Cloud website ([Click Here](https://cloud.arduino.cc)) and register there.
- Once registered, go to the `Devices` section and add a new device.
- Select third-party device and ESP8266. After that, select the model of NodeMCU you have from the drop down menu. Click on continue.
- Give it an appropirate name and click on continue. 
- A device ID and a secret key are generated. Save them safely, as we will need them later in the process.
<br/>

***Creating a Thing :***  
A thing is the main project area where the code is written. It associates the device we created in the previous step with the code. Follow the below steps to create a new thing.  
- Once a devie is created, head over to the `Things` section and create a new thing.
- You can rename the thing, and then add some variables that are required. 
- Now, in the `Associated Device` section, click on `Select Device`.
- In the new window opened, select the device previously created, to associate with the thing.
- Just below is a `Network` sub-section. Select `Configure` option and enter your WiFi details in the provided space.
- Also, enter the secret key that was generated previously. 
<br/>

***Coding the NodeMCU :***  
Most of the code is pre-written by the Arduino Cloud, and we just need to do some changes inside the functions. First, head over to the `Sketch` sub-section under the `Things` section. For each variable that is added into the thing, there is a function that is associated with the variable. This variable is what syncs the data between the cloud and the devices. If you selected the variable to be of `On Change` type, then the function corresponding to the variable will get executed everytime the value of the variable changes. But if you select the variable to be of `Periodically` type, then the value of the variable is refreshed periodically and the function related to the variable executes if there any change in it's value is observed.  

Make required changes to the pre-written code and then select the compile option on the top left. After successful compilatioin, you can then upload the code to the NodeMCU. Note that you will need Arduino Create Agent running before you can upload the code, else the device will not get detected. For any errors regarding compiling or uploading, please check the [Troubleshoot Section](https://github.com/Bharadwaj-R/NodeMCU-and-Arduino-Cloud/edit/main/Troubleshoot.md#Troubleshoot).

You can even code using Arduino IDE, but make sure you install `Arduino_ConnectionHandler` and `ArduinoIoTCloud` libraries, and any other associated libraries that the Arduino IDE suggests you to install.  
<br/>

***Setting up the Dashboard :***  
Once the coding part is done, head over to the `Dashboards` section and proceed to creating your first dashboard. Follow the below steps to create a dashboard.
- Click on the Untitled part to rename the Dashboard to any name of your liking.
- Now, go to the Add dropdown and select the type of widget that you would like to add.
- In the new window that opens, type in a name for your widget, and link a variable to the widget. You can customize the widget a little too.
- Click on Done once everything is setup.
- You can change between Mobile view and Computer view by clicking on the small Mobile icon that appears right side of Add dropdown.
- Finally, click on the small eye button to the left of Add dropdown to save your Dashboard. You can click on the small pencil icon there to edit the dashboard whenever required.

That's it for the creation of dashboard. Once you uploaded the code into the NodeMCU, use the dashboard to control/monitor the connected variables.  
<br/>

### So, what next?  

Thats it for the basics of NodeMCU and Arduino Cloud. Yay!!! Now, it is time for some basic projects and advanced learning. Head over to my profile [Click Here](https://github.com/Bharadwaj-R) and check out my other repositories for some example projects using NodeMCU and Arduino Uno. Consider leaving a follow and star the repositories if you like them. Thanks!!
