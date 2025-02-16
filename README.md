# Logan Home Lab

## Overview
This is a snapshot of my personal home lab, which serves a dual purpose: providing essential personal amenities while acting as a sandbox for experimenting with new operating systems and software. Beyond hands-on experience with various operating systems, I also refine my skills in firewall rule management, Cisco CLI, and virtual machine backup strategies. This is an evolving project, and I am excited to expand and enhance it as my knowledge and expertise grow.

## Objectives
- Learn and experiment with self-hosted services.
- Implement virtualization and containerization.
- Configure a secure and scalable network.
- Configure network and VLANs
- Implement firewall rules and monitor logs

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

## Screenshots

These are a few screenshots of some of the services I have currently installed. This is an ongoing project and is dynamic in nature. 

Proxmox Dashboard

![Proxmox Screen](https://github.com/user-attachments/assets/ee2cdc43-4b39-4241-83b8-7c2ebff5c9da)

OPNsense Firewall with Zenarmor Dashboard

![Firewall Screen Shot](https://github.com/user-attachments/assets/b780116f-d0a4-40c0-b19e-1951b9839d61)

TAK Server Metrics Dashboard

![TAK Server Dashboard](https://github.com/user-attachments/assets/ba553cd3-dc80-4867-9cf2-a0e77f4617b3)

Next Cloud Dashboard

![Next Cloud](https://github.com/user-attachments/assets/313088ec-5f36-4be0-a474-e4596925c123)
