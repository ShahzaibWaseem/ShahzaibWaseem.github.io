---
title: Garduino
date: 2018-07-20
categories:
  - Projects
tags:
  - C
  - Microcontroller
  - projects
toc: true
toc_label: "Table of Contents"
toc_icon: "cog"
toc_sticky: true
---

**Languages Used**: C/C++

**Source Code**: [GitHub Link](https://github.com/ShahzaibWaseem/Project-COAL)

## Goal
The Goal of this project was to provide a cost efficient solution, to automate a Garden, which can be built by almost anybody with little experience of hardware and computer code. Similar DIY projects like this cost almost $200 - $350 on websites like [KickStarter](https://www.kickstarter.com/projects/mattiaslepp/the-smart-garden-your-solution-for-better-food), this system would cost fraction of its price. Similarly, the project may be hooked up to the WiFi using applications/services like Blynk.

## Requirements
### Dependencies
- Arduino IDE

### Hardware Required
- Arduino UNO or any other Arduino board
- A generic Breadboard
- Jumper wires
- Water pipes
- Battery
- Some resistors
- Water motor
- 5V relay module (acts as a switch)
- Real Time Clock (RTC)
- Soil Moisture Sensor
- Light Dependent Resistor (LDR)

## Description
This project was built using an Arduino Microcontroller to automate the Gradening Process, with the usage of Real Time Clock (RTC), to monitor when to water the plants and how long to water, Soil Moisture Sensor, another parameter which tells how much to water, Light Dependent Resistor (LDR), to tell at what time of the day to water in case the RTC fails. Input sensors were logged on the computer, temporarily, using the Arduino IDE, The System can be connected to services like Blynk and many others.

### Schematic Diagram
![Garduino Schematic Diagram](https://camo.githubusercontent.com/0d0ad706e00fdae810f4814c53148a8075e3ddb0/687474703a2f2f692e696d6775722e636f6d2f7a7764694238462e706e67)

## References
The Schematic image was borrowed from this [GitHub repository](https://camo.githubusercontent.com/0d0ad706e00fdae810f4814c53148a8075e3ddb0/687474703a2f2f692e696d6775722e636f6d2f7a7764694238462e706e67), although this is not the exact schematic used in my project.

The idea of this project was inspired by this [video](https://www.youtube.com/watch?v=O_Q1WKCtWiA) on YouTube.

Check this [website](https://arduinogetstarted.com/tutorials/arduino-relay) to see how a relay works.

You can fork the project on [GitHub](https://github.com/ShahzaibWaseem/Project-COAL) to add more features to the project.