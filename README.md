# LoRaWAN experimental network deployment guide
## Eindhoven University of Technology
### 5LIC0 - Networked Embedded Systems
This repository contains guide and resources to quickly deploy an experimental LoRaWAN network. It contains guides for various nodes and gateways, as well as setting up network server locally or in cloud with The Things Stack.

# Table of Contents
1. [Setting up Network Server](#network-server)
    * [The Things Stack Community Edition](#tts-community)
    * [The Things Stack On-Premise Local Deployment](#tts-local)

2. [Creating Application and Adding Integrations](#network-server)

3. [Setting up and deploying nodes](#setting-up-nodes)
    * [B-L072Z-LRWAN1 STM32 Discovery Kit](#discovery-kit)
    * [Nucleo-L073RZ Dev Board with I-NUCLEO-LRWAN1 LoRa Sensor Expansion Board](#nucleo-node)

4. [Setting up and deploying gateway](#setting-up-gw)
    * [Nucleo-F746ZG Dev Board with Gateway Expansion Board](#nucleo-gateway)
    * [The Things Indoor Gateway](#ttig)
    * [Tektelic Kona Micro](#kona)
    * [Mikrotik LoRa wAP](#mikrotik)

____________________________________
1. ### Setting up Network Server<a name="network-server">
    A standard used in this setup is [The Things Stack](https://www.thethingsindustries.com/stack/?gclid=CjwKCAjwzaSLBhBJEiwAJSRokmPnIF06ZFI6BN1JdGJh4u5DG9k_ul6xIc6FFRCxZ5r3cKdzENMUuBoCJwkQAvD_BwE) - a LoRaWAN network server implementation by [The Things Network](https://www.thethingsnetwork.org) (and subsequently [The Things Industries](https://www.thethingsindustries.com)). This choice was made due to it being high
    on features (new LoRaWAN standards are implemented very quickly), open-source (github [here](https://github.com/TheThingsNetwork/lorawan-stack))
    and rich in documentation and community support.
    It is possible to use the community cloud version, that is deployed globally and operated by TTN, as well as deploy an independent instance of the stack.
    The latter provides more versatility in terms of customization, as well as autonomicity, while community network provides vanilla flow that is extremely easy and fast to start with.
    * #### The Things Stack Community Edition<a name="tts-community">
    Using this option boils down to creating an account in the community network server.
    Adding an application, gateways and devices is described in the further parts
    of the manual (see table of contents).
    * #### The Things Stack On-Premise Local Deployment<a name="tts-local">
    

2. ### Creating Application and Adding Integrations<a name="network-server">

3. ### Setting up and deploying nodes<a name="setting-up-nodes">
    This part is dedicated to configuring the example firmware for the nodes 
    building it and flashing it to the device.
    The base for the firmware was chosen to be arm mbedOS (other possibilities and motivation for this choice are described in the high-level report).
    * #### Toolchain setup<a name="toolchain">
    mbedOS allows for various ways to create and cross-compile the firmwares, namely:
    - mbed online compiler
    - toolchain and codebase on local machine
    * #### B-L072Z-LRWAN1 STM32 Discovery Kit<a name="discovery-kit">
    * #### Nucleo-L073RZ Dev Board with I-NUCLEO-LRWAN1 LoRa Sensor Expansion Board<a name="nucleo-node">
    [This link](https://os.mbed.com/platforms/ST-Nucleo-L073RZ/) contains description of the board pinout, as well as other specifications and documents.

4. ### Setting up and deploying gateways<a name="setting-up-gw">
    * #### Nucleo-F746ZG Dev Board with Gateway Expansion Board<a name="nucleo-gateway">
    * #### The Things Indoor Gateway<a name="ttig">
    * #### Tektelic Kona Micro<a name="kona">
    * #### Mikrotik LoRa wAP<a name="mikrotik">
