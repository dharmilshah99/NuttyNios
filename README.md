# NuttyNios

## 1 Introduction
### 1.1 Overview

Nutty Nios is a real-time multiplayer browser game based on Konami's Dance Dance Revolution. The game involves players tilting their FPGA to correspond with arrows shown on the browser, and can support up to four players playing at once.

<p align="center">
    <img src="https://user-images.githubusercontent.com/83905363/194340645-79f14a4b-345b-4ffc-aee2-1f78f0a6684d.png"/>        
    <img src="https://user-images.githubusercontent.com/83905363/194340692-ad31c5ee-c802-4e73-a5e3-14644796d5d9.png"/>
    <img src="https://user-images.githubusercontent.com/83905363/194340703-7a0a3c6b-aad6-406d-9228-f8cee085697f.png"/>
</p>

During development, design decisions were made to ensure Nutty Nios was **responsive**, **portable** and **secure**. To meet these requirements, Nutty Nios was evaluated on its node's resource utilization as well as node to gateway and gateway to server round trip times.

### 1.2 Funcctional Requirements

The following features of Nutty Nios fulfills the minimum functional requirements of the system:
- Local processing of Accelerometer Data: The FPGA performs fixed point FIR filtering on data from its accelerometer sensor to smoothen it.
- Communicating Information from Node to Server: The FPGA's accelerometer data is processed by a gateway (local computer) to compute the tilt direction of the board. Directions are then published to a secure MQTT broker hosted on AWS.
- Establishing a Cloud Server to Process Events: A Colyseus Server hosted on AWS computes the next state of the game depending on directions published to the MQTT broker.
- Communicating Information from the Server back to the Nodes: The FPGA toggles between sets of filter coefficients depending on the mode of the game - easy or hard - chosen by a player.

## 2 Demonstration

<div align="center">
  <video src="https://user-images.githubusercontent.com/83905363/194345566-c557f36b-cb5b-4745-b131-ef5d05416b11.mp4" width=600/>
<div/>


    
