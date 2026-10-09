# Lab 6 Immich (photo backup) 

## Deployment
Immich is multi container where it'll have four services that can talk on a shared network.
Using docker compose: Depends_on will make sure the containers start in the correct order.
<img width="139" height="108" alt="image" src="https://github.com/user-attachments/assets/5667b868-8c80-46ce-99fd-077cb8e7b032" />

## The install

[X] Login & check IP remained static

**Make a new directory called Immich, then check with:** ls

**CLI:** cd immich

**Download official docker compose file;**
- https://github.com/immichapp/immich/releases/latest/download/docker-compose.yml

**CLI:** wget -O docker-compose.yml 

**Download the environment file;** 
- https://github.com/immichapp/immich/releases/latest/download/example.env

**CLI:** wget -O .env 

**Make a directory;**
**CLI:** mkdir -p library postgres 

**Check to make sure it was made:** 
**CLI:** ls

<img width="346" height="80" alt="image" src="https://github.com/user-attachments/assets/3fd68dda-20dc-4396-848e-bd2fab71eefe" />

**.yml file:**

<img width="321" height="574" alt="image" src="https://github.com/user-attachments/assets/679e61bc-e926-45bc-ac3d-b64fb9748978" />

### Note
List, -a for All

**CLI:** ls -a
 nano .env
 
### Note
Control  X to escape

**CLI:** docker compose up
**Try logging in remotely via browser;** http://192.168.0.79:2283/

<img width="165" height="187" alt="image" src="https://github.com/user-attachments/assets/4dcfd4db-ebc5-4a7b-8d86-be7f4fe59c1b" />
<img width="137" height="186" alt="image" src="https://github.com/user-attachments/assets/b7716e6e-7d5d-433d-a69c-a8be342f691c" />

## Success!

Log out;
**CLI:** 

docker compose down

exit

