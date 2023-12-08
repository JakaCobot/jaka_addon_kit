
# DH Gripper AddOn
---
**This AddOn is suitable for DH Gripper PGE series. It includes gripper command blocks and gripper control page.**

## AddOn Information

* Name: dh_custom_cmd
* Version: v2.2

## Installation Guide

* System Requirements:

    Controller: v1.7.1.19 and above  
    App: v1.7.1.16 and above  
    JAKA-AddOn-Kit: v1.3 and above  

* Installing the AddOn

    Open the App-Settings-System Settings-Add-ons, click the "+" button in the upper right corner, and install the AddOn.

    <div align="center"><img width="700" src="./img/Install_AddOn.png"/></div>

* Gripper Installation

    1. Connect through the control cabinet RS485 channel.

    <div align="center"><img width="500" src="./img/cab485.png"/></div>

    2. Connect the gripper to the TIO interface using the dedicated JAKA cable provided by DH.

    <div align="center"><img width="500" src="./img/TIO485.png"/></div>


## Configuration Guide

* Configuring the AddOn

    Run the plugin, click the "gear" button in the plugin operation options bar to enter the configuration page.

    <div align="center"><img width="700" src="./img/AddOn_Config.png"/></div>

    1. Socket port: The gripper custom command uses socket communication and will occupy a socket port. If there is a conflict, the port number can be modified.
    2. Modbus type: Gripper connection method selection. Choose TIO if connected through the end TIO, and choose Cabinet if connected through the control cabinet RS485.

* Communication Configuration

    Configuration for TIO connection:
    1. Configure the analog input channel, reuse it as RS482 channel 2.

    <div align="center"><img width="500" src="./img/TIO_channel.png"/></div>

    2. Add signals: status_init, status_run, speed, force, position.

    <div align="center"><img width="500" src="./img/signals.png"/></div>

    Connection through the control cabinet RS485:
      1. Ensure that the gripper's slave ID is 1, baud rate is 115200, data bit length is 8, stop bit length is 1, and no parity.

## Usage Instructions

**Command Blocks**
In the App programming page-Extensions, find the gripper command blocks.

<div align="center"><img width="800" src="./img/Gripper_Command.png"/></div>

1. Initialize Gripper: Two initialization methods are available, refer to the DH Gripper user manual for details.
2. Control Gripper: Support speed (1-100), force (20-100), position control (0-100). All units are in percentage, exceeding the upper/lower limits will be considered as using the upper/lower limits.
3. Get Gripper Status: Initialization status (0,1,2), holding status (0,1,2), position. Returns data in string format.

**Control Page**
In the Add-ons page, find the "Earth" button in the operation options column of the AddOn, click to open the control page.

<div align="center"><img width="800" src="./img/找到控制页面.png"/></div>

* Usage Example

<div align="center"><img width="800" src="./img/Program.png"/></div>


## **Troubleshooting**

* Common Issues
  None at the moment

<!-- * AddOn Logs

If the plugin generates log files, it should be explained how to view and analyze these logs to solve problems. -->

## **Updates and Upgrades**

<!-- * Update Guide

Provide instructions on how to obtain and install the plugin for updates. -->

**Version History**

* v2.2.0

    * Developed based on AddOn3.0, supports control cabinet rs485 and TIO.
    * Developed based on PGE series communication manual.
    * Control page support

**Support and Contact Information**

* Learn more about [AddOn information](https://jakacobot.github.io/guide/addOn/aboutaddOn.html)
* Learn the [development tutorial](https://jakacobot.github.io/guide/addOn/demo_DHGripper.html) for this AddOn.

**AddOn Acquisition Method**

* Contact JAKA sales or technical personnel to obtain.
* Download and package it yourself through GitHub, [click here to jump](https://github.com/JakaCobot/jaka_addon_kit/tree/main/Template).
