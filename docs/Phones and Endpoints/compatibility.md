# Compatibility Chart

This is a full compatibility chart of all phones tested with the LTS Community PBX. Only phones that have been tesed will be listed here. This list is maintained by the community. **JUST BECAUSE A PHONE IS NOT LISTED HERE DOES NOT MEAN IT WILL NOT WORK**

## Status

| Status                 | Meaning                                                                 |
|------------------------|-------------------------------------------------------------------------|
| Fully Compatible       | Device fully works with the LTS Community PBX as intended by the OEM.   |
| Fully Functional       | Device works with the LTS Community PBX with no or minimal issues, but not in a way intended by the OEM. |
| Experimental           | Device does not fully work, but we are actively working to improve support. |
| Limited Support        | Device does not fully work, and we do not plan to improve support.       |
| Not Working (Experimental) | Device does not work, but we are trying to find ways to make it work.     |
| Not Working            | Device does not work, and we do not plan to support it.                 |
| Unsupported            | Device requires proprietary protocols, software, or tools we cannot use. |


## 3CX

| Model              | Device Type             | Status                   |
|--------------------|-------------------------|--------------------------|
| 3CX App            | Desktop/Mobile Softphone| Unsupported              |
| 3CXPhone           | Desktop Softphone       | Fully Compatible         |
| Cloud PBX          | UCaaS IP-PBX            | Fully Compatible         |

## Acrobits

| Model          | Device Type      | Status                   |
|----------------|------------------|--------------------------|
| Acrobits       | Mobile softphone | Fully Compatible         |
| Cloud Softphone| Mobile softphone | Unsupported              |
| Groundwire     | Mobile softphone | Fully Compatible         |
| Linkup         | Mobile softphone | Experimental             |

## Android Open Source Project

| Model          | Device Type      | Status                   |
|----------------|------------------|--------------------------|
| Dialer         | Mobile softphone | Fully Compatible         |

## Cisco/Linksys/Sipura
[^1]: HTTP provisioning is only supported in frimware 9-4. If using an older frimware, the device will have limited functionality if TFTP is not available. Using 9-4 is recommended.
[^2]: Device does not support HTTP provisioning, the device will have limited functionality if TFTP is not available.

| Model          | Device Type      | Status                   |
|----------------|------------------|--------------------------|
| CP7942 (SCCP)  | IP Phone         | Fully Functional[^1] |
| CP7942 (SIP)   | IP Phone         | Not working, Experimental[^1]|
| CP7965 (SCCP)  | IP Phone         | Fully Functional[^1]}       |
| CP7962 (SIP)   | IP Phone         | Not working, Experimental[^1]|
| CP7970 (SCCP)  | IP Phone         | Fully Functional[^1]         |
| CP7975 (SCCP)  | IP Phone         | Fully Functional[^1]         |
| CP7975 (SIP)   | IP Phone         | Not working, Experimental[^1]|
| CP7811         | IP Phone         | Fully Functional when using a CHAN_SIP (CISCO) extension, advanced features do not work on a normal CHAN_SIP extension, phone can not receive calls or auto-hangup on a PJSIP extenson.|
| CP7811-3PCC    | IP Phone         | Fully Compatible         |
| CP7821         | IP Phone         | Fully Functional when using a CHAN_SIP (CISCO) extension, advanced features do not work on a normal CHAN_SIP extension, phone can not receive calls or auto-hangup on a PJSIP extenson.|
| CP7821-3PCC    | IP Phone         | Fully Compatible         |
| CP7841         | IP Phone         | Fully Functional when using a CHAN_SIP (CISCO) extension, advanced features do not work on a normal CHAN_SIP extension, phone can not receive calls or auto-hangup on a PJSIP extenson.|
| CP7841-3PCC    | IP Phone         | Fully Compatible         |
| CP7861         | IP Phone         | Fully Functional when using a CHAN_SIP (CISCO) extension, advanced features do not work on a normal CHAN_SIP extension, phone can not receive calls or auto-hangup on a PJSIP extenson.|
| CP7861-3PCC    | IP Phone         | Fully Compatible         |
| CP8841         | IP Phone         | Fully Functional when using a CHAN_SIP (CISCO) extension, advanced features do not work on a normal CHAN_SIP extension, phone can not receive calls or auto-hangup on a PJSIP extenson.|
| CP8841-3PCC    | IP Phone         | Fully Compatible         |
| CP8845         | IP Phone         | Fully Functional when using a CHAN_SIP (CISCO) extension, advanced features do not work on a normal CHAN_SIP extension, phone can not receive calls or auto-hangup on a PJSIP extenson.|
| CP8845-3PCC    | IP Phone         | Fully Compatible         |
| CP8851        | IP Phone         | Fully Functional when using a CHAN_SIP (CISCO) extension, advanced features do not work on a normal CHAN_SIP extension, phone can not receive calls or auto-hangup on a PJSIP extenson.|
| CP8851-3PCC    | IP Phone         | Fully Compatible         |
| CP8861         | IP Phone         | Fully Functional when using a CHAN_SIP (CISCO) extension, advanced features do not work on a normal CHAN_SIP extension, phone can not receive calls or auto-hangup on a PJSIP extenson.|
| CP8861-3PCC    | IP Phone         | Fully Compatible         |
| CP8865         | IP Phone         | Fully Functional when using a CHAN_SIP (CISCO) extension, advanced features do not work on a normal CHAN_SIP extension, phone can not receive calls or auto-hangup on a PJSIP extenson.|
| CP8865-3PCC    | IP Phone         | Fully Compatible         |
| CUCM           | Software IP-PBX  | Only works with an IP-auth based extension with port fowarding due to lack of support for SIP trunk registration. It's recommended to use CUBE, FreePBX, or Asterisk as a SBC.       |
| CUBE           | SBC              | Fully Compatible         |
| CME            | Software IP-PBX  | Fully Compatible         |
| IP Communicator (SCCP) | Windows Softphone | Fully Functional (requires router that handles TFTP properly, or local TFTP server)[^2]|
| SPA1000        | 1-line ATA       | Fully Compatible         |
| SPA112         | 2-line ATA       | Fully Compatible         |
| SPA122         | 2-line ATA/router| Fully Compatible         |
| SPA2102        | 2-line ATA/router| Fully Compatible         |
| SPA525G (SIP)  | IP Phone         | Fully Compatible         |
| SPA525G2 (SIP) | IP Phone         | Fully Compatible         |
| SPA525G2 (SCCP)| IP Phone         | Partially Compatible, Experimental (Phone freezes upon incoming call, outgoing works) |
| PAP2T          | 2-line ATA       | Fully Compatible         |

## FusionPBX

| Model    | Device Type      | Status                   |
|----------|------------------|--------------------------|
|FusionPBX |Software IP-PBX   |Fully Compatible          |

## Grandstream

| Model  | Device Type            | Status                        |
|--------|------------------------|-------------------------------|
| GRP2612| IP Phone               | Fully Compatible              |       
| HT801  | 1-line ATA             | Fully Compatible              |
| HT802  | 2-line ATA             | Fully Compatible              |
| HT818  | 8-line ATA/Router      | Fully Compatible              |
| UCM6102| IP-PBX Appliance       | Fully Compatible              |       
| UCM6202| IP-PBX Appliance       | Fully Compatible              |       
| WP810  | Cordless Wi-Fi IP Phone| Limited Support (Experimental)|       


## Issabel Project

| Model          | Device Type      | Status                   |
|----------------|------------------|--------------------------|
|Issabel         |Software IP-PBX   | Fully Compatible         |

## MDev Group

 Model           | Device Type      | Status                   |
|----------------|------------------|--------------------------|
|MicroSIP        |Windows Softphone | Fully Compatible         |

## Microsoft

| Model          | Device Type      | Status                   |
|----------------|------------------|--------------------------|
|Response Point  |IP-PBX Appliance  | Fully Compatible         |

## Mitel

## Obihai

## Polycom

| Model                   | Device Type      | Status                   |
|-------------------------|------------------|--------------------------|
|VVX101                  |IP Phone          | Fully Compatible         |
|VVX150                  |IP Phone          | Fully Compatible         |
|VVX150 (OBi edition)    |IP Phone          | Fully Compatible         |
|VVX201                  |IP Phone          | Fully Compatible         |
|VVX250                  |IP Phone          | Fully Compatible         |
|VVX250 (OBi edition)    |IP Phone          | Fully Compatible         |
|VVX300                  |IP Phone          | Fully Compatible         |
|VVX301                  |IP Phone          | Fully Compatible         |
|VVX310                  |IP Phone          | Fully Compatible         |
|VVX311                  |IP Phone          | Fully Compatible         |
|VVX350                  |IP Phone          | Fully Compatible         |
|VVX350 (OBi edition)    |IP Phone          | Fully Compatible         |
|VVX400                  |IP Phone          | Fully Compatible         |
|VVX401                  |IP Phone          | Fully Compatible         |
|VVX410                  |IP Phone          | Fully Compatible         |
|VVX411                  |IP Phone          | Fully Compatible         |
|VVX450                  |IP Phone          | Fully Compatible         |
|VVX450 (OBi edition)    |IP Phone          | Fully Compatible         |
|VVX500                  |IP Phone          | Fully Compatible         |
|VVX501                  |IP Phone          | Fully Compatible         |
|VVX600                  |IP Phone          | Fully Compatible         |
|VVX601                  |IP Phone          | Fully Compatible         |
|VVX1500                 |IP Phone          | Fully Compatible         |
|VVXD60                  |IP Phone          | Fully Compatible         |
|VVXD230                 |IP Phone          | Fully Compatible         |


## Sangoma/Digium/Schmooze

| Model          | Device Type      | Status                   |
|----------------|------------------|--------------------------|
|A25             |IP Phone          | Fully Compatible         |
|Asterisk 18     |Software IP-PBX   | Fully Compatible         |
|Asterisk 19     |Software IP-PBX   | Fully Compatible         |
|Asterisk 20     |Software IP-PBX   | Fully Compatible         |
|Asterisk 21     |Software IP-PBX   | Fully Compatible         |
|Asterisk 22     |Software IP-PBX   | Fully Compatible         |
|D60             |IP Phone          | Fully Compatible         |
|D65             |IP Phone          | Fully Compatible         |
|FreePBX 15      |Software IP-PBX   | Fully Compatible         |
|FreePBX 16      |Software IP-PBX   | Fully Compatible         |
|FreePBX 17      |Software IP-PBX   | Fully Compatible         |
|P310            |IP Phone          | Fully Compatible         |
|P315            |IP Phone          | Fully Compatible         |
|P320            |IP Phone          | Fully Compatible         |
|P325            |IP Phone          | Fully Compatible         |
|P330            |IP Phone          | Fully Compatible         |
|P370            |IP Phone          | Fully Compatible         |
|P310            |IP Phone          | Fully Compatible         |
|PBXact          |Software IP-PBX   | Fully Compatible         |
|S206            |IP Phone          | Fully Compatible         |
|S305            |IP Phone          | Fully Compatible         |
|S406            |IP Phone          | Fully Compatible         |
|S505            |IP Phone          | Fully Compatible         |
|S705            |IP Phone          | Fully Compatible         |
|Switchvox 80    |IP-PBX Appliance  | Fully Compatible         |
|Switchvox 310   |IP-PBX Appliance  | Fully Compatible         |
|Switchvox 450   |IP-PBX Appliance  | Fully Compatible         |
|Switchvox 470   |IP-PBX Appliance  | Fully Compatible         |

# SignalWire

| Model          | Device Type      | Status                   |
|----------------|------------------|--------------------------|
|FreeSWITCH      |Software IP-PBX   | Fully Compatible         |

## Yealink

