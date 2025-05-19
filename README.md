# Network-utilities-demos

# NMAP Demo

## Introduction

The tech world can be a bit funny sometimes, consider the world of cyber security - outside of classified digital forensics tools available to law enforcement, everyone has the same toolbox. The good guys (and girls) and the bad guys (and girls) both have the same requirements, and do broadly the same things on a day to day basis, it's just that the good team is allowed to do it. 

For example, they both want to gather information about the devices across an infrastructure, and check for vulnerabilities - one side to attack, the other to defend.

Malicious attackers are generally referred to as `Black Hat` hackers, whereas those *using their powers for good*, are known as `White Hat` or `Ethical` hackers.

Some organisations may employee White Hat hackers, although they'll likely not have that job title. Many are also independent, contracting with companies temporarily, or they could be part of an organisation which offers security services, such as penetration (pen) testing to others.

Another example of a common toolset is `Kali Linux` which comes pre-configured with a wide range of penetration testing and digital forensics tools. Of course it's designed for ethical hackers and cybesecurity professionals, but there's nothing preventing attackers from using it!

## Network Discovery using NMap

NMap is a network discovery tool which can be used to identify hosts, their open ports, and various other details across a target network. 

We can give it a try using our CentOS VM, but we need to change some settings from their defaults in VirtualBox. 

- Switch your VM network adapter option from `NAT` to `Bridged Adapter`.
        It is likely that your `first boot` snapshot is from a running VM, but this means that when you launch it the previous configuration it retained by the VM, even though you changed the VirtualBox settings. To fix this simply shutdown your VM **don't restore another snapshot**, and restart. It should then request and receive an IP on your network.
- You will not be able to connect to `localhost`, so login via vbox window and then check the IP with `ip a`.
- Connect as normal, but use ssh [**username**]@[**IP address**]
- Install nmap with `sudo dnf install nmap -y` then try the following commands:
    - Scan your network with `sudo nmap -sL 192.168.1.0/24` or `sudo nmap -sn 192.168.1.0/24` - **compare the differences**
    - Start to gather info about a host with `sudo nmap -Pn [target IP]`
    - See running services and versions with `sudo nmap -sV [target IP]`
    - Use `man`, `--help`, and further research to discover other options.
