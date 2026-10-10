# Lab 9 Reverse Proxy/ NGINX

## What was built
**Reverse proxy concepts through a GUI**

- The NGINX engine handles the actual HTTP routing.
- NPM Admin UI Runs at server-ip:81 Add proxy hosts, request certificates.
- NPM writes real nginx config files for you, same results a sysadmin would hand-write in production.

This will bring our separate networks into a shared network, simplifying our life.

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

<img width="336" height="339" alt="Screenshot 2026-10-10 at 2 51 40 PM" src="https://github.com/user-attachments/assets/0b2c93cf-fba5-4664-b7c7-106e7ff84d76" />


**CLI:**

docker compose up -d

<img width="565" height="80" alt="Screenshot 2026-10-10 at 2 50 20 PM" src="https://github.com/user-attachments/assets/313ec70e-7808-4a3c-bc90-89eeedbacb70" />


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
Add proxy hostname/ IP:
Port:

SSL;
- Request a new certificate (for https)
- Credential file content (to help create https certificate): (this is where your token goes)
- Propagation (30sec)

**Create user API Tokens**

<img width="468" height="338" alt="image" src="https://github.com/user-attachments/assets/3fc57a26-a3f4-4b62-bd4f-fddf3ec85dcf" />


<img width="468" height="609" alt="image" src="https://github.com/user-attachments/assets/573a07e1-02d2-4aff-93f3-08e9823557e8" />


<img width="468" height="470" alt="image" src="https://github.com/user-attachments/assets/6342a291-edcb-4334-8bf3-980b96dc3282" />

**This will create your DNS API token from Cloudflare.** 

**Through your browser log into NGINX & add proxy host & paste in your token.**

<img width="385" height="648" alt="image" src="https://github.com/user-attachments/assets/c68373cf-6056-4822-88ec-847ca996175c" />

**It can take some time to populate in Nginx:**

<img width="468" height="123" alt="image" src="https://github.com/user-attachments/assets/286be924-17ae-45d8-be9c-26fd52b12c3a" />

**Back to Cloudflare to add a record:**


<img width="468" height="273" alt="image" src="https://github.com/user-attachments/assets/33f5e294-56f8-40c9-8ac1-1fd872a7e65c" />

**Looking at our connection security after doing the same for Filebrowser & we are secure:**

<img width="323" height="286" alt="image" src="https://github.com/user-attachments/assets/a89f70ef-192f-46c8-9633-ecdef84d8168" />

<img width="321" height="287" alt="image" src="https://github.com/user-attachments/assets/77f53af0-e1e2-48c0-9f53-49f83518398d" />
