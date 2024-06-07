
# DH Gripper AddOn
---
**This AddOn is suitable for DH Gripper PGE series, including gripper command blocks and gripper control page.**

## AddOn Information

* Name: dh_custom_cmd
* Version: v2.3

## Installation Guide

* System Requirements:

    Controller: v1.7.1.19 and above  
    App: v1.7.1.16 and above  
    JAKA-AddOn-Kit: v1.3 and above  

* Install the AddOn

    Open the App-Settings-System Settings-Add-on, click the "+" button in the upper right corner, and install the AddOn.

    <div align="center"><img width="700" src="/addon/dh_custom_cmd/doc/img/Install_AddOn.png"/></div>

* Connect the Gripper

    Method one: Connect through the control cabinet's RS485 channel.

    <div align="center"><img width="500" src="/addon/dh_custom_cmd/doc/img/cab485.png"/></div>

    Method two: Connect the gripper to the robot's TIO interface by using the JAKA dedicated TIO connection cable provided by DH.

    <div align="center"><img width="500" src="/addon/dh_custom_cmd/doc/img/TIO485.png"/></div>


## Configuration Guide

* Configure the AddOn

    Run the AddOn, click the "gear" button in the operation options bar to enter the configuration page.

    <div align="center"><img width="700" src="/addon/dh_custom_cmd/doc/img/AddOn_Config.png"/></div>

    Socket port: The gripper custom command uses socket communication and will occupy a socket port. If there is a contradiction, the port number can be modified.

    Modbus type: Gripper connection method selection. Choose TIO if connected through the end TIO, and choose Cabinet if connected through the control cabinet RS485.

* Configure the Communication

    **When configure the TIO, you should:**
    
    Step 1: Configure the analog input channel, reuse it as RS482 channel 2.
    
    <div align="center"><img width="500" src="/addon/dh_custom_cmd/doc/img/TIO_channel.png"/></div>

    Step 2: Configure Modbus parameter.

    <div align="center"><img width="800"  src="/addon/dh_custom_cmd/doc/img/tio485_Setting.png"/></div>

    Step 3: Add signals: status_init, status_run, speed, force, position.
    
    <div align="center"><img width="500" src="/addon/dh_custom_cmd/doc/img/signals.png"/></div>


    
    **When connecting through the control cabinet RS485, you should:**

    Step 1: Switch the Modbus type in the AddOn configuration to cab.
    Step 2: Make sure the gripper is off IO mode.
    Step 3: Ensure that the gripper's slave ID is 1, baud rate is 115200, data bit length is 8, stop bit length is 1, and no parity.

    Then you can use it directly without any other configuration of the controller.

## Instructions

**Command Blocks**
In the App's programming page-Extensions, find the gripper command blocks, which have three types.

<div align="center"><img width="800" src="/addon/dh_custom_cmd/doc/img/Gripper_Command.png"/></div>

Type One

Initialize Gripper: Two initialization methods are available, refer to the DH Gripper user manual for details.

Type Two

Control Gripper: Support speed (1-100), force (20-100), position control (0-100). All units are in percentage, if the set value has exceeded the upper/lower limits, it will be considered as using the upper/lower limits.

Type Three

Get Gripper Status: Initialization status (0,1,2), holding status (0,1,2), position. Return value is in string format.

**Control Page**
In the Add-on page, find the "Earth" button in the operation options column, click to open the control page.

<div align="center"><img width="800" src="/addon/dh_custom_cmd/doc/img/找到控制页面.png"/></div>

* Example

<div align="center"><img width="800" src="/addon/dh_custom_cmd/doc/img/Program.png"/></div>


## **Troubleshooting**

* Common Issues
  None at the moment

<!-- * AddOn Logs

If the addon generates log files, it should be explained how to view and analyse these logs to solve problems. -->

## **Updates and Upgrades**

<!-- * Update Guide

Provide instructions on how to obtain and install the addon for the newest version. -->

**Version History**

* v2.2.0

    * Developed based on AddOn3.0, supports control cabinet RS485 and TIO.
    * Developed based on PGE series communication manual.
    * Control page support.

**Support and Contact Information**

* Learn more about [AddOn information](https://jakacobot.github.io/guide/addOn/aboutaddOn.html)
* Learn the [development tutorial](https://jakacobot.github.io/guide/addOn/demo_DHGripper.html) for this AddOn.

**How to Get AddOn Packages**

* Contact JAKA sales or technical personnel to obtain.
* Download it through GitHub, [click here to jump](https://github.com/JakaCobot/jaka_addon_kit/tree/main/Template).
