# Module 01 - Basic Connection and end-host config.
CCNA1-Lab-Mod01_03-Static_IP


## Introduction
As a new junior network engineer on the job at Corpo Prime Capitalism InCorporated, your senior has asked you to wire a basic network for interns to begin the great task maximizing profits!

This network consists of 4 PCs a switch (2960) and router (2911).

The router has been pre-configured by someone on the network admin team, and your predecessor has tried **everything** (*according to them*) but the PCs are not able to communicate.

You've been given the topology information (*below*). Using your superlative skills review the information, reconnect the devices to specification, and ensure communication using the **ping** utility.

...and remember the creed of **Corpo Prime Capitalism InCorporated**:
Maximize the glory of endless profits!


## Topology 
![Topology](https://raw.githubusercontent.com/jadamhunt/CCNA/main/mod01/CCNA1-Mod01_03-topo-Static_IP.png)


## Schema
**Domain:** netech.lab

| Device | Interface | Connected To | IP Addess | Notes |
|:-:|-|-|-|-|
|**R1 (2911)**| G0/0 | S1  (G0/1)| *provided* |  |
||||||
|**S1 (2960)**| G0/1 | R1 (G0/0)|  |  |
|-| Fa0/1| PC 10_1 (Fa0) |  |  |
|-| Fa0/2| PC 10_2 (Fa0) |  |  |
|-| Fa0/3| PC 10_3 (Fa0) |  |  |
|-| Fa0/4| PC 10_4 (Fa0) |  |  |
||||||
|**PC 10_1**|Fa0|S1 (Fa0/1)|192.168.1.101| static |
|**PC 10_2**|Fa0|S1 (Fa0/2)|192.168.1.102| static |
|**PC 10_3**|Fa0|S2 (Fa0/1)|192.168.1.103| static |
|**PC 10_4**|Fa0|S2 (Fa0/2)|192.168.1.103| static |



## Instructions
### Infrastructure Devices
All wiring should be in alignment with specifications listed in the topology schema.

#### Routers
##### `R1 (2911)` 
  - Router description needs to be changed to `R1`.  
  - No further configuration is required.

#### Switches
##### `S1 (2960)` 
  - Switch description needs to be changed to `S1`.
  - This network requires only basic `packet forwarding`. No configuration required.

#### End Devices
##### (4) PCs
  - PC descriptions need to be changed *respectively* to: 
    - `PC_01`
    - `PC_02`
    - `PC_03`
    - `PC_04`

  - IP Addresses need to be statically set to:
    - `192.168.1.101` - `104` 
    - Assume all subnet masks are `255.255.255.0`.
    - Configure each gateway address to `192.168.1.1`.




### Services:
No services to configure in this assignment.



### Activities
  - Ensure you can ping from `PC_01` to `PC_04` using the command line `ping` utility.
  - Once you've confirmed the successful ping, use Packet Tracer's built in Simple PDU generator (Details in Notes). 
  - Create a Complex PDU originating from PC_02.
    - Application: `PING`
    - Destination IP Address: `192.168.1.1`
    - Source IP Address: `192.168.1.102`
    - TTL: `32`
    - TOS: 0
    - Sequence Number: `1`
    - Size: `32`
    - One Shot Time: `1` second.

#### Notes
You will have to wait until S1 ports fully negotiate with hosts before pings are successful.

To use the PDU Generator, click the icon of the small (*closed*) envelope in the top tool bar. Your mouse cursor will turn to an envelope with a `+` plus symbol. Click on `PC_01` for the ping `source` then click on `PC_04` for the ping `destination`.

The bottom right section which has, up to this time, been empty space will now show a representation of the ping and it's status, indicating among other things, chiefly:
  - Status
  - Source
  - Destination
  - Type
  
Status should be **Successful**. To complete this assignment.

## Summary
In this assignment you have statically configured end devices to be members of the same network. Additionally, you've used the basic troubleshooting utility `ping` to confirm end-to-end connectivity.

Remember that end-to-end communication requires the following to succeed:
  - Addressing
  - Path
  - Destination

**Great work!**
