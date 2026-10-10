# Lab 8 Uptime-Kuma

## What Was Built

An uptime monitor for our services with alert options.

## Resources

Official Uptime Kuma website:
- https://uptimekuma.co/

Offical Uptime Kuma GitHub repository:
- https://github.com/louislam/uptime-kuma

https://hub.docker.com/r/louislam/uptime-kuma

## The journey getting there

**Create uptime-kuma directory & load .yml file via nano:**

<img width="346" height="61" alt="image" src="https://github.com/user-attachments/assets/777215a2-cb34-4679-9a0a-26f373ee8f98" />

**.yml file (correct indentation/ mapping):**

services: 
  uptime-kuma: 
   image: louislam/uptime-kuma:2 
   container_name: uptime-kuma 
   volumes: 
    - ./uptime-kuma-data:/app/data 
   ports: 
    - "3001:3001"
   restart: unless-stopped 

**CLI:**

docker compose up

<img width="386" height="121" alt="image" src="https://github.com/user-attachments/assets/ab197f53-3e00-49f0-807a-c2ef9f6be2b0" />

**log in through browser:**
192.168.0.79:3001/setup-database

<img width="356" height="231" alt="image" src="https://github.com/user-attachments/assets/58e522bd-7e7e-4162-b102-f9e5bd0d4814" />

**Create a SQLite database:**

<img width="352" height="135" alt="image" src="https://github.com/user-attachments/assets/5cd35081-9a58-4715-9a27-8c45f381f4ec" />

**Now to add some monitors:**

<img width="468" height="222" alt="image" src="https://github.com/user-attachments/assets/ffcf3a65-46f9-4462-9c15-c06c72624d9e" />

**Uptime Kuma can’t read the custom url; vault.lab**

<img width="468" height="217" alt="image" src="https://github.com/user-attachments/assets/13b804de-f641-4bab-937c-438723b2cf01" />

Vaultwarden 
Monitor type: HTTP(s) Check interval: 60s 
In kuma docker compose we need to add: 

- extra_hosts: - "vault.lab:192.168.0.79"

**Must go to CLI Uptime-Kuma & update the .yml file:**

<img width="271" height="126" alt="image" src="https://github.com/user-attachments/assets/0a884235-13c8-4533-9cdb-7738c2b9d5b0" />

**Container remade (no need to ‘docker compose down’ as the change is so small.**

<img width="468" height="114" alt="image" src="https://github.com/user-attachments/assets/93130703-614e-406d-888c-f0669da5ec75" />

**Now Vaultwarden is running:**

<img width="205" height="192" alt="image" src="https://github.com/user-attachments/assets/5fa40b9c-0237-44de-9a7f-4463e9207057" />

## Notifications & Alerts

**Go to uptime-kuma & select a service & click edit: **

- http://192.168.0.79:3001/edit/2

Then: setup notification via Telegram app using bot named @botfather;

<img width="233" height="471" alt="image" src="https://github.com/user-attachments/assets/e70b8bfc-961c-4021-91a8-bbf6429bd6bf" />

<img width="202" height="473" alt="image" src="https://github.com/user-attachments/assets/292d9df2-1ae3-4b75-8721-cc1d16f8893e" />

### Telegram

In Telegram find @botfather type into the chat: /newbot
Name it: XXXXXXX
Pick a unique name; XXXXXXX
It will give you a token to access the HTTP API: (keep secure)

Type name into search 
Type a simple message to activate bot @ /start: hi
Did twice then receive a ‘Chat ID’ in notification setup;
- XXXXXXX

Enable default & apply to all existing monitors, then test & check for a telegram message, then save.

<img width="636" height="806" alt="Screenshot 2026-10-10 at 1 37 48 PM" src="https://github.com/user-attachments/assets/00879836-0ef0-4f2f-b561-5f17b6743894" />

**Now test by shutting down a service via docker compose.**

**Showed on uptimekuma as ‘down’, then received a notice via telegram:** [File browser] down

**CLI:**

Docker compose up

**Telegram service alerts:** ‘UP’ 200-OK

- If using a service here, setup an alert to go to email.

## Tips
When something breaks: 

- Check the monitor type first, then the port, then the network. That sequence solves most issues.

Settings:

- Try setting a ‘Retry’ to double check there is a problem in the uptime kuma Edit page.

