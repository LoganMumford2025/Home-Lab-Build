# Logan Home Lab

## Table of Contents

- [Overview](#overview)
- [Objectives](#objectives)
- [Hardware Setup](#hardware-setup)
- [Software Stack](#software-stack)
- [Network Diagram](#network-diagram)
- [Challenges & Solutions](#challenges--solutions)
- [Key Learnings](#key-learnings)
- [Next Steps & Improvements](#next-steps--improvements)
- [Documentation & Screenshots](#documentation--screenshots)
- [Conclusion](#conclusion)

## Overview
This is a snapshot of my personal home lab, which serves a dual purpose: providing essential personal amenities while acting as a sandbox for experimenting with new operating systems and software. Beyond hands-on experience with various operating systems, I also refine my skills in firewall rule management, Cisco CLI, and virtual machine backup strategies. This is an evolving project, and I am excited to expand and enhance it as my knowledge and expertise grow.

## Objectives
- Learn and experiment with self-hosted services.
- Implement virtualization and containerization.
- Configure a secure and scalable network.
- Configure network and VLANs
- Implement firewall rules and monitor logs
- Known environment to test/ practice new software and OS for current and future jobs

## Hardware Setup
| Component   | Model/Specs  |
|------------|-------------|
| Server     | Homemade Server |
| Storage    | 4x 8Tb HDD in RAIDZ1, 2x 4Tb Samsung 2.5" SSD 1x 16Tb HDD (Samba Storage) 1x Samsung 512Gb M.2 Boot Drive |
|Routers     | ASUS ASUS RT-BE86U Wifi 7 Router, GL.iNet GL-MT3000 (Beryl AX) Router, ISP provided router |
| Switch     | Cisco CBS 350 16 Port Switch|
| Firewall   | Protectli Vault 4 Port with OPNsense with Zenarmor Layer 7 Inspection |

## Software Stack
| Category       | Software |
|---------------|----------|
| Hypervisor    | Proxmox PVE|
| Containers    | Next Cloud, Wazuh SIEM, Word Press |
| Virtual Machines | Windows 10 Pro, Samba, Plex, Splunk, TAK Server, Windows Server 2022, Kali Linux |
| OS           | Ubuntu, Windows, OPNsense|
| Network      | Cisco, OPNsense |

## Network Diagram

![Home Lab](https://github.com/user-attachments/assets/187eb1d2-44f2-4950-99ed-2d7ee63c990e)

## Challenges & Solutions

- **Problem:** Couldn’t initialize HDD's on Proxmox withoug wiping drives first. This was annoying. I was hoping to bring a movies library over, plug and play style, for my Plex server.
- **Solution:** I ended up splitting my movies library between a couple of external HDDs and then wipinga and initializing internal HDDs in Proxmox.
- **Problem** I was worried about HDD failure and availability of my video library HDD's.
- **Solution** I decided to create a ZFS pool of hard drives and put them in Raid 1 (RAIDZ1). This configuration would allow for one hard drive failure of my movie library and would be able to rebuild that HDD once another HDD was plugged in. I haven't tested this feature yet, as I haven't had any HDD failures, and according to the S.M.A.R.T scan that Proxmox does, all HDD's are healthy.
- **Problem** Even with a RAID configuration, this does not qualify as a back up per se. If there are two HDD failures in close succession all dat on the ZFS cluster would be lost.
- **Solution** I created a VM (SAMBA) with an attached 16Tb HDD that would serve as a back up storage independent of the ZFS array. This is still on premise and shares the same power supply and a few other dependencies as the ZFS pool, but is a step in the right direction. In addition to a library backup, I also use the 16Tb drive as a share drive between other virtual machines on the Proxmox Node as well as my home pc and laptop all on the same network. Samba is great because it bridges the compatability between Linux file systems and Windows file systems and allows data to be stored regardless of OS.
- 

## Key Learnings

- Linux has a lot of dependencies. After installing the initial linux OS, any version, be ready to download more packages for some functionality. Net-tools, nano editor, etc.
- I suck at Virtual Networks. Couldn't get a virtual network configured properly to hide the gateway in order to create a safe sandbox to play with bad things. This will be a future problem when I dabble with viruses later down the line.
- Linux CLI language is not Cisco Switch CLI language. I wish it was.
- Learned a lot of Linux CLI. Definitely would love to take a course on Linux administration.
- Dabbled with python scripts and modified some configuration files (without making backup copies) whoops! Not good. Breaking the only copy of a configuration file lead from VM's working great to not at all and banging my head against the wall shaming myself for tinkering and trying to do something pointless when the whole thing worked to begin with.
- Don't fix it if it isn't broken!!

## Next Steps & Improvements

- Implement a virtual network for certain projects so they can see or find the gateway for security reasons. Sandboxed projects with Kali Linux or working with malware.
- Automate tasks using PowerShell or Python scripts. Nothing runs on scripts yet like auto update or email updates on node status etc.
- Learn to read and be more efficient with understanding SIEM (Splunk and Wazuh). I hope to be able to fine tune alerts and be able to dismiss many due to not really being relevant alerts.
- Learn to network better. My networking skills need work to better configure this entire setup for a more efficient method of packet transmission.

## Documentation & Screenshots

These are a few screenshots of some of the services I have currently installed. This is an ongoing project and is dynamic in nature. 

Proxmox Dashboard

![Proxmox Screen](https://github.com/user-attachments/assets/ee2cdc43-4b39-4241-83b8-7c2ebff5c9da)

OPNsense Firewall with Zenarmor Dashboard

![Firewall Screen Shot](https://github.com/user-attachments/assets/b780116f-d0a4-40c0-b19e-1951b9839d61)

TAK Server Metrics Dashboard

![TAK Server Dashboard](https://github.com/user-attachments/assets/ba553cd3-dc80-4867-9cf2-a0e77f4617b3)

Next Cloud Dashboard

![Next Cloud](https://github.com/user-attachments/assets/313088ec-5f36-4be0-a474-e4596925c123)


## Conclusion
- This was and still is a fun project. This is an ongoing project and I am excited to create and expand on my current setup. There have been long sleepless nights dreaming of configuration problems and trying to work out why something isn't working correctly. This project is my favorite and has hooked me big time. It's a love hate. I love when things work and there have been times when I was ready to take a sledge hammer to the whole thing. However, most of my projects are used to tinker and learn. I hope to use this lab in the future to better understand enterprise level setups and hopefully as place to practice skills and "try things" that wouldn't be allowed in a workplace environment.


