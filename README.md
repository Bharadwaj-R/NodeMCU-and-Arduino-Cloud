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

Make required changes to the pre-written code and then select the compile option on the top left. After successful compilatioin, you can then upload the code to the NodeMCU. Note that you will need Arduino Create Agent running before you can upload the code, else the device will not get detected. If you are unable to upload the code, but your compilation is successful, please check the [Troubleshoot Section](https://github.com/Bharadwaj-R/NodeMCU-and-Arduino-Cloud/edit/main/README.md#troubleshoot) at the end of the article for any possible solution.

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

### Troubleshoot
***1. Code Compiled successfully, but not able to upload to NodeMCU :***  
This problem generally comes up with generic NodeMCU boards. To solve the issue, click on the `Open Full Editor` option in the Sketch sub-section. You will be redirected to Arduino Create online editor. Click on the dropdown menu available and then on Select Board and Port. In the new window that opens, search for ESP8266 and select `Generic ESP8266 Module`. Select the port to which the NodeMCU is connected. Now in the `Flavours` menu, make sure all the specifications indicated match with your NodeMCU board. If everything is correct, then go to the Reset Methods and select `nodemcu` from the dropdown. Try uploading the code now.  

Another possible solution is to use Arduino IDE offline application. As mentioned above, head over to the Full Editor and from the three-dot menu, select `Download Sketch` option. Once download finishes, extract the `.zip` file and open the `.ino` file. Make sure you type in your WiFi details in the `arduino_secrets.h` file along with the secret key. Verify the device ID in `thingProperties.h` file. Try to compile and upload now.  

***2. Code compiled and uploaded successfully, but NodeMCU doesn't connect to WiFi :***  
A possible issue can be one of these - incorrect WiFi SSID, Password, Device Secret Key, or device ID. Verify all the details in the code. If all the previously mentioned parameters are correct, then check if the WiFi you are trying to connect is 2.4GHz or 5GHz frequency. Most of the NodeMCUs only support 2.4GHz frequency, so verify if the WiFi you provided is of 2.4GHz frequency. Allow atleast 10 seconds for the device to connect to WiFi.  

***3. Arduino Cloud doesn't detect my NodeMCU :***  
Firstly, check if Arduino Create Agent is running in the background. If not, then download and open the Arduino Create Agent. Your device must be detected now. If the problem still persists, try uploading a sample code to the NodeMCU using Arduino IDE offline. If the latter is not successful too, then install/update the drivers of the NodeMCU and try again. If nothing from the above works, maybe the NodeMCU is a faulty one. Exchange it for a new device.  

### So, what next?  

Thats it for the basics of NodeMCU and Arduino Cloud. Yay!!! Now, it is time for some basic projects and advanced learning. Head over to my profile [Click Here](https://github.com/Bharadwaj-R) and check out my other repositories for some example projects using NodeMCU and Arduino Uno. Consider leaving a follow and star the repositories if you like them. Thanks!!
