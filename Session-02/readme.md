# Week 02 - Linux Ubuntu and SSH

## What I built

Installed Ubuntu Server 24.04 on a virtualbox VM and connected it to SSH from my host  machine

## Virtual Machine Server Specs
- RAM 4096 MB
- Disk 25 GB
- OS Ubuntu Server 24.04
- Network Bridged Adapter
- Hostname 'Ubuntu-lab'
- Username 'labuser'

## Server IP Address

- IP: '192.168.0.58'

## Commands I ran

Updating the server
```

sudo apt update
sudo apt upgrade
```

Check disk space
```
df -h

Check memory use
```
free -h
```
Connect via SSH
```
ssh labuser@192.168.0.58
```
## Observations
1. The server has 15 GB free after installation
2. RAM useage was at 500 MB at idle
3. The SSH connection was instant after first connection was established
4. SSH has remembered the VM as trusted connection after confirming first connect

## Session Checklist
- [x] Ubuntu server installed
- [x] SSH access confirmed

## Problems

See 'troubleshooting.md' for the first issue and resolution
