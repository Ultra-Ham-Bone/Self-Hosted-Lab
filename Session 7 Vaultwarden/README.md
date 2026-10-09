# Lab 7 Vaultwarden

## What Was Built

A lightweight open source implementation of the Bitwarden server for a self hosting password manager.
Runs locally aside other containers.

## Deployment

Via Docker Compose alongside the other containers

### To Begin

Make a directory
cd
upload via nano

**CLI:**

nano docker-compose.yml

<img width="286" height="170" alt="image" src="https://github.com/user-attachments/assets/22abb1c2-62f1-4685-b5d2-3a6d8d43ea50" />

**CLI:**

docker compose up

<img width="351" height="277" alt="image" src="https://github.com/user-attachments/assets/634789e0-9d1e-4928-b952-384fddd7b0d3" />

Log in over browser: 192.168.0.79:8083

<img width="289" height="244" alt="image" src="https://github.com/user-attachments/assets/447ff37e-2455-4bab-bdab-f93a76b821b6" />

### Tip
‘Control K’ may delete faster

New .yml 

**CLI:** 

nano docker-compose.yml (incorrect formatting .yml code)

<img width="382" height="236" alt="image" src="https://github.com/user-attachments/assets/9ad462d6-02b3-4220-b84b-a9b0b2d254be" />

**CLI:** 

nano vaultwarden.env

<img width="460" height="59" alt="Screenshot 2026-10-09 at 12 44 55 PM" src="https://github.com/user-attachments/assets/98682304-b1e2-41aa-ba2b-4bfaceb16a03" />

Open another HOST terminal:

**CLI:** 

sudo nano /etc/hosts 

Add at the bottom (your own IP): 
192.168.XXX.XX vault.lab 

Try docker compose up & returns ‘invalid spec’;

<img width="468" height="68" alt="image" src="https://github.com/user-attachments/assets/36b17bc0-1050-4035-b6bc-1cd6a80a67ac" />

Fixed the .yml file & success: (docker compose up)

<img width="399" height="337" alt="Screenshot 2026-10-09 at 12 48 20 PM" src="https://github.com/user-attachments/assets/f87fc23c-5b21-49d9-bc06-8dac0782ee96" />

Shut down & restart, Login in through browser works using address: 
http://192.168.XXX.XXX:8082/login

<img width="146" height="196" alt="image" src="https://github.com/user-attachments/assets/cccdfe8c-8b42-4881-822b-472d2e012ca2" />

