# NodeRED-Photon-TempMonitoring
Using IBM Cloud's NodeRED and a Particle Photon microcontroller, monitor temperature and receive predictions

## This is the NodeRED flow for a laboratory temperature monitoring system
The purpose of this project is to create a prototype of a temperature monitoring system that could be used in various laboratory instruments such as fume hoods, incubators, fridges, etc. Receiving and storing tempertaure readings wirelessly elimates manual recording, saves time, ensures accuracy, and reduces logbook clutter. Alerts and maintenance predictions will notify the user when an instrument is performing poorly or needs to be checked. This makes it easy for the user to plan their schedule for when the instrument will need its next calibration.

## Hardware:
* Particle Photon with connected LM35 temperature sensor, connected to your device's WiFi network (Photon is programmed on Particle IDE **this code not included**)

Enter your device details in the `SSE device` nodes. If using another sensor like an Arduino or Raspberry Pi, the sensor input nodes will have to be changed 

##  Software:
* IFTTT account
* IMB Cloud account for access to NodeRED and Cloudant database (free account is o.k.)

## The flow includes:
1. Dashboard visuals of current temperature and temperature over time
2. Dtabase storage in Cloudant (feature of IBM Cloud)
3. Alerts
  1. Alert on the Dashboard
  2. Email Alert through IFTTT
4. Health status of the temperature sensor
5. Prediction of when the instrument will need claibration

### Dashboard temperature visuals
- Will be updated every time the Photon pushes data to NodeRED (dependant on the interval programmed on the Particle IDE)
- Can change the layout of the line graph to display different time intervals

### Database storage
- Create a Cloudant database and connect it to your NodeRED flow
- Change the data logging frequency

### Alerts
- Set your desired min/max temperatures that will tigger the alert
- Hook to IFTTT account

###  Health of Temperature Sensor
- This is dependant on the temperature sensor type that is used. Here, LM35 is used. Change the error vlaue depending on the type of sensor you are using, which can be found on the product's data sheet

###  Predictions
- The max/min temperatures can be set in the `Output a prediction` node 
