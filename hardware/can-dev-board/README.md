# CAN Development Board

- [Objective](#Objective)
- [Boards](#Boards)
    - [__can-dev-board-v1.0__](https://github.com/engeniusua/pcb-warehouse/tree/master/hardware/can-dev-board/v1.0)
- [Architecture Analysis](#Architecture-Analysis)
- [Components choice and Analysis](#Components-choice-and-Analysis)
    - [CAN Network](#CAN-Network)
        - [Overview](#Overview)
        - [Topology](#Topology)
        - [List of available Components](#List-of-available-Components)
        - [Chosen Components](#Chosen-Components)
## Objective

The main focus of this board is to provide a wide choice development environment for the __CAN network prototyping__. 

The components were chosen based in prior analysis of the network needs. With that in mind, the board tries to provided a wide redundant choice of components, with the same functionality, ranging in prince and features.

>It is important to __maintain the development environment as similar to the production__ one. This provides __consistency__ and __avoids bugs__ when migrating from environments.

## Boards

| Name | Updates | Last Updated | Tested |
|------| ------- |------------|--------------|
| [__can-dev-board-v1.0__](https://github.com/engeniusua/pcb-warehouse/tree/master/hardware/can-dev-board/v1.0) | First version | 28 May 2019 | :red_circle: |

## Architecture Analysis

The board has to provide __multiple options__ in the different areas. With that in mind, it will have _"redundant"_ components that might be used during prototyping phase.

The microcontroller used must have top performance and features count. This way is possible to develop with a wide range of options and then spec down in production.

The chosen _platform_ is from [Microchip](https://www.microchip.com/) with a __PIC architecture microcontroller__. This option was based on pure preference, since is taught at Aveiro's University microcontroller related subjects.

## Components choice and Analysis

### CAN Network

#### Overview

The CAN Network can be implemented using [CAN](https://en.wikipedia.org/wiki/CAN_bus) classic standard or the latest [CAN FD](https://en.wikipedia.org/wiki/CAN_FD) standard with data rates up to `8 Mbit/s` (__CAN FD supports backward compability with the classic CAN__). Might be useful to provide both standards for development.

#### Topology

In production a CAN hardware _topology_ must be used, considering __cost__ and __functionality__, one of the options listed below might be implemented:

- __Topology 1__: 
    - Microcontroller
    - CAN Controller 
    - CAN Transceiver
- __Topology 2__:
    - Microcontroller with integrated CAN Controller 
    - Transceiver
- __Topology 3__:
    - Microcontroller 
    - CAN controller with integrated CAN Transceiver

Studying the options, the most viable implementations are __Topology 1 and 2__. __Topology 1__ might be usefull for CAN FD, since only [dsPICs](https://erika.tuxfamily.org/wiki/index.php?title=Microchip_dsPIC) (_that might be useful to look in too_) are available with integrated CAN FD controllers. __Topology 2__ is the most viable aproach for the classic CAN standard since there are a lot of PIC microcontrollers available with integrated classic CAN controllers.

It is important to provide the options during development to ease of prototyping and avoid problems during migration to production, so both topologies 1 and 2 should be supported in the development board.

#### List of available Components

The lists of components provided by __Microchip__ can accessed in the following links:

- [CAN transceivers](https://www.microchip.com/ParamChartSearch/Chart.aspx?branchID=1932)
- [CAN Controllers](https://www.microchip.com/ParamChartSearch/Chart.aspx?branchID=1939)
- [CAN Controllers with Integrated Transceiver](https://www.microchip.com/ParamChartSearch/Chart.aspx?branchID=1938)
- [Microcontrollers with built in CAN controller](https://www.microchip.com/ParamChartSearch/Chart.aspx?branchID=50)
- [Microcontrollers with built in CAN controller with support for CAN FM](https://www.microchip.com/ParamChartSearch/Chart.aspx?branchID=51#)

#### Chosen Components

- __Microcontroller__ [PIC32MX795F512L](https://www.microchip.com/wwwproducts/en/PIC32MX795F512L) - provides all the features and a huge amount of i/o to connect all modules. Main features:
    - 80MHz/105DMIPS, 32-bit MIPS M4K® Core
    - USB 2.0 On-The-Go Peripheral with integrated PHY
    - 10/100 Ethernet MAC with MII/RMII Interfaces
    - __2 x CAN2.0b modules with 1024 buffers__
    - 8 Dedicated DMA Channels for USB OTG, Ethernet, and CAN
    - 5 Stage pipeline, Harvard architecture

- __CAN Transceiver__: 

- __CAN Controller__:




