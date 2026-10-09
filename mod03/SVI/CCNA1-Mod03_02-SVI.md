# Module 03 - Switch Virtual Interface (SVI)
**Activity:** Lab  
**Name:** CCNA1-Lab-Mod03_02-SVI
**Author:** Prof. J.Hunt  
**Version:** 1.2 (2026)  


## Introduction
As a junior network engineer on the job at Corpo Prime Capitalism InCorporated, it has been mandated that all intermediate network devices are reachable by in-band-access methods. The problem is, your colleagues are unable to separate themselves from HR's mandatory Plant Petting for Stress and Deescalation training.

It's up to you, to save your team from bureaucracy! Configure the SVI on your floor's layer 2 device and let nothing distract your from the great task maximizing profits!

This network consists of 1 PC, a switch (2960), and router (2911).

The router has been pre-configured with an IP address on interface G0/0, but attempts to telnet to have failed and long since been abandoned.

You've been given the topology information (*below*). Using your superlative skills review the information, reconnect the devices to specification, ensure communication using the **ping** utility, and ensure in-band access via telnet from PC0.

...and remember the creed of **Corpo Prime Capitalism InCorporated**:
Maximize the glory of endless profits!


## Topology 

![Topology](https://raw.githubusercontent.com/jadamhunt/CCNA/main/mod03/CCNA1-Mod03_02-topo-SVI.png)

## Schema
**Domain:** netech.lab

| Device | Interface | Connected To | IP Addess | Subnet| Notes |
|:-:|-|-|-|-| - |
|**R1 (2911)**| G0/0 | S1  (G0/1)| 192.168.1.1 | 255.255.255.0 |
||||||
|**S1 (2960)**| G0/1 | R1 (G0/0)| - | - |
|-| Fa0/1| PC0 (Fa0) | - | - |
|-| VLAN 1| - | 192.168.1.11  | 255.255.255.0 |
||||||
|**PC 0**|Fa0|S1 (Fa0/1)|192.168.1.100| 255.255.255.0 |



## Instructions
### Infrastructure Devices
All wiring should be in alignment with specifications listed in the topology schema.

#### Routers
##### `R1 (2911)` 
  - Router description needs to be changed to `R1`.  
  - Initial configuration
    - Service Password Encryption
    - Enable password set to `cisco`
    - Banner: # R1 Banner #
    - Console
      - Password set to `class` and enabled
      - Logging Synchronous
      - Executive Timeout disabled
    - Vty lines (0 - 15)
      - Password set to `class` and enabled
      - Logging Synchronous
      - Executive Timeout disabled
      - Transport input to allow all traffic

#### Switches
##### `S1 (2960)` 
  - Switch description needs to be changed to `S1`.
  - Initial configuration
    - Service Password Encryption
    - Enable password set to `cisco`
    - Banner: # R1 Banner #
    - Default gateway set to `192.168.1.1`
    - Console
      - Password set to `class` and enabled
      - Logging Synchronous
      - Executive Timeout disabled
    - Vty lines (0 - 15)
      - Password set to `class` and enabled
      - Logging Synchronous
      - Executive Timeout disabled
      - Transport input to allow all traffic
    - Interface VLAN 1
      - IP Address `192.168.1.11` 
      - Subnet Mask `255.255.255.0`
 

#### End Devices
##### (1) PCs
  - PC descriptions need to be changed *respectively* to: 
    - `PC0`
  - IP Addresses statically set
  - Assume all subnet masks are `255.255.255.0`
  - Configure each gateway address to `192.168.1.1`

### Services:
No services to configure in this assignment.

### Activities
  - Ensure you can ping from `PC_0` to `S1` using the command line `ping` utility.
  - Using the command line telnet utility, telnet to S1 using the following command: `telnet 192.168.1.11`

#### Notes
You will have to wait until S1 ports fully negotiate with hosts before pings are successful.

To use the PDU Generator, click the icon of the small (*closed*) envelope in the top tool bar. Your mouse cursor will turn to an envelope with a `+` plus symbol. Click on `PC_01` for the ping `source` then click on `PC_04` for the ping `destination`.

The bottom right section which has, up to this time, been empty space will now show a representation of the ping and it's status, indicating among other things, chiefly:
  - Status
  - Source
  - Destination
  - Type
  
Status should be **Successful**. To complete this assignment.

## Deliverable
Your deliverable for this assignment will be a screenshot of:

  - the Summary Page showing completion points
  - Telnet from PC0 to S1

## Summary
In this assignment you have enabled a Layer 2 switch to participate in IP as member of the network, in addition to setting up the VLAN interface. Congrats!

**Great work!**
