# LoRaWAN experimental network deployment guide
## Eindhoven University of Technology
### 5LIC0 - Networked Embedded Systems
This repository contains guide and resources to quickly deploy an experimental LoRaWAN network. It contains guides for various nodes and gateways, as well as setting up network server locally or in cloud with The Things Stack.

Perform this to load the example project for the nodes prior to continuing with
the manual

```bash
➜ git submodule init
➜ git submodule update
```

# Table of Contents
1. [Setting up Network Server](#network-server)
    * [The Things Stack Community Edition](#tts-community)
    * [The Things Stack On-Premise Local Deployment](#tts-local)

2. [Creating Application and Adding Integrations](#network-server)

3. [Setting up development environment](#setting-up-env)
    * [Using Mbed CLI and GNU Arm embedded toolchain](#toolchain)
        - [Preparing and compiling the project for the first time](#first-compile)
    * [Using Mbed online compiler](#online-compiler)

4. [Setting up and deploying nodes](#setting-up-nodes)
    * [B-L072Z-LRWAN1 STM32 Discovery Kit](#discovery-kit)
    * [Nucleo-L073RZ Dev Board with I-NUCLEO-LRWAN1 LoRa Sensor Expansion Board](#nucleo-node)

5. [Setting up and deploying gateway](#setting-up-gw)
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

    To create an account, go to https://console.cloud.thethings.network and choose the region (most probably it will be EU)

    ![image](./res/cluster-picker.png) 

    If you don't yet have an account - register and then log in to the console with your account. If you see the screen below - you are ready to add your applications, gateways and devices, all of which are described in subsequent steps.

    ![image](./res/ttn-account.png) 

    * #### The Things Stack On-Premise Local Deployment<a name="tts-local">
    _TODO_
    
____________________________________
2. ### Creating Application and Adding Integrations<a name="network-server">

____________________________________
3. ### Setting up development environment<a name="setting-up-env">
mbedOS allows for various ways to create and cross-compile the firmwares, namely:

* #### Using Mbed CLI and GNU Arm embedded toolchain <a name="toolchain">
This variant allows for working wit the code and cross-compiling locally.

More details about installing the Mbed CLI 2 (including Windows), as well as dependencies can be found [here](https://os.mbed.com/docs/mbed-os/v6.15/build-tools/mbed-cli-2.html).

Below the install
Prerequisites (for Unix systems):
 - Make sure you have Python 3.6 or higher, and the corresponding development package (i.e. `python3-dev`)
 - Install [CMake](htps://cmake.org/install/)
 - Install [Ninja ](https://github.com/ninja-build/ninja/wiki/Pre-built-Ninja-packages)
 - Install [GNU Arm Embedded Toolchain](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads)

After the prerequisites are satisfied, create a virtual environment in the root
of this repository for installing python packets to avoid conflicts with the
host packets

```bash
➜ python3 -m venv env_mbed
➜ source ./env_mbed/bin/activate

# To deactivate the virtual environment use
➜ deactivate
```

After activating the virtual environment install the Mbed CLI, and make sure that
`~/.local/bin` is in the path


```bash
➜ python -m pip install mbed-tools

# If ~/.local/bin not in PATH
➜ PATH="$PATH:~/.local/bin"
```
##### Preparing and compiling the project for the first time<a name="first-compile">
Navigate to the directory with the project (e.g. `./mbed-os-example-lorawan` in this repository) and prepare the project:

```bash
➜ mbed_tools deploy
Checking out all libraries to revisions specified in .lib files. Resolving any unresolved libraries.
The following library dependencies were fetched: 

Library Name    Repository URL                      Path                                                                     Git Reference
--------------  ----------------------------------  -----------------------------------------------------------------------  ---------------
mbed-os         https://github.com/ARMmbed/mbed-os  /Users/ivanturasov/5lic_repo/repository/mbed-os-example-lorawan/mbed-os  master
```
Now the project is ready for building, refer to [project readme](./mbed-os-example-lorawan/README.md)


* #### Using Mbed online compiler<a name="online-compiler">
____________________________________

4. ### Node-specific configurations<a name="setting-up-nodes">
    This part is dedicated to configuring the example firmware for the nodes 
    building it and flashing it to the device.
    The base for the firmware was chosen to be arm mbedOS (other possibilities and motivation for this choice are described in the high-level report).

    
    
    - mbed online compiler
    
    * #### B-L072Z-LRWAN1 STM32 Discovery Kit<a name="discovery-kit">
    * #### Nucleo-L073RZ Dev Board with I-NUCLEO-LRWAN1 LoRa Sensor Expansion Board<a name="nucleo-node">
    [This link](https://os.mbed.com/platforms/ST-Nucleo-L073RZ/) contains description of the board pinout, as well as other specifications and documents.
____________________________________

5. ### Setting up and deploying gateways<a name="setting-up-gw">
    * #### Nucleo-F746ZG Dev Board with Gateway Expansion Board<a name="nucleo-gateway">
    * #### The Things Indoor Gateway<a name="ttig">
    * #### Tektelic Kona Micro<a name="kona">
    * #### Mikrotik LoRa wAP<a name="mikrotik">
