# waveformsIOT
Sample Industrial IOT Project Using the Digilent Waveforms Analog Discovery 2 Data Acquisition Pod

## Hardware

Linux-Windows-Mac-RaspberryPi Computer

RaspberryPi IoT Endpoint (Optional)

Arduino Uno (or other Arduino - assumes you know how to use)

## Software
Python3 Programming Language
PIP3 Python Package Manager
NodeJS JavaScript Runtime
NPM Node Package Manager
IBM Node-Red Flow-Based Programming Tool
Mosquitto MQTT Message Queue

##Description
The Digilent Analog Discovery 2 data acquistion pod from Digilent is used to monitor voltage levels being generated by Pin 13 on an Arduino (alternates from 0 to 5V using a varying period).

Python is used to create a Waveforms SDK API client that measures the voltages on the two scope channels.  At every reading Python publishes a reading to the MQTT queue using the paho-mqtt client.

Application logic is in IBM Node-Red. The message queue is subscribed to.  When readings appears on the MQTT queue, they are read and stored in a MongoDB collection.

A webpage is created in Node-Read that allows a user to view the most recent Voltage readings.
