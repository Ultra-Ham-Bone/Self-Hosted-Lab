# Lab 9 Reverse Proxy/ NGINX

## What was built
**Reverse proxy concepts through a GUI**

- The NGINX engine handles the actual HTTP routing.
- NPM Admin UI Runs at server-ip:81 Add proxy hosts, request certificates.
- NPM writes real nginx config files for you, same results a sysadmin would hand-write in production.

## Resources

Nginx Proxy Manager
- https://nginxproxymanager.com/

Nginx Proxy Manager documentation
- https://nginxproxymanager.com/guide/

## Lets have a look through the process

**CLI:**

docker network create proxy

**To verify:**

docker network inspect proxy

<img width="726" height="809" alt="Screenshot 2026-10-10 at 1 58 39 PM" src="https://github.com/user-attachments/assets/58526696-3ebf-4e18-b582-b23e9b6ca593" />

**To install:**

mkdir nginx
cd nginx

<img width="216" height="54" alt="image" src="https://github.com/user-attachments/assets/22b2e5ad-38a7-45d6-9f97-505c9ad399f2" />

**CLI:**

nano docker-compose.yml

services:
  npm:
    image: 'jc21/nginx-proxy-manager:latest'
    restart: unless-stopped
    ports:
      - '80:80'
      - '443:443'
      - '81:81'
    volumes:
      - ./data:/data
      - ./letsencrypt:/etc/letsencrypt
    networks:
      - proxy

networks:
  proxy:
    external: true

**CLI:**

docker compose up -d

<img width="432" height="113" alt="image" src="https://github.com/user-attachments/assets/bbbcba9a-f43c-4a1e-b273-f0ca77520bde" />

**Log in to NGINX & create account:**

<img width="194" height="210" alt="image" src="https://github.com/user-attachments/assets/43a8f4ae-178e-44d3-b102-cf6d879745ac" />

**Create an Admin account in NGINX:**

XXXXXXX@XXX.com
Create proxy hosts

**Go back into all the folders & Add to every docker .yml file:**

<img width="148" height="87" alt="Screenshot 2026-10-10 at 2 11 26 PM" src="https://github.com/user-attachments/assets/6ac4a8fd-f7eb-47e2-b167-80e7d9743cbc" />

**Then go back through and do** ‘docker compose up’ **for each.**

## Cloudflare

Make account
Create a domain
Under dns records
- subdomain (one service per)

Dash.cloudflare.com
Add a record

On nginx
Add proxy host
Port:

SSL;
- Request a new certificate (for https)
- Credential file content (to help create https certificate): (this is where your token goes)
- Propagation (30sec)



