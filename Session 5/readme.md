# Lab 5 File Browser

### Notice
File Browser is closing down on September 2026 https://hacdias.com/2026/07/28/filebrowser/

## What was built
File browser is a web-based file manager that gives private access to files on a VM through a browser, from any device on my network. It is similar to a cloud storage device or Google drive.

### Deployment
- Using Docker Compose
- Writing a yml file via nano docker-compose.yml

## What happened on our way to the goal

**Create filebrowser directory via ssh**

<img width="468" height="145" alt="image" src="https://github.com/user-attachments/assets/76560ca9-ffe7-4555-bfc4-fcb2e25dc6dc" />

**load in .yml file**

<img width="468" height="179" alt="image" src="https://github.com/user-attachments/assets/fb08ee72-66ea-4d5a-b5d8-d8cfa2e40b72" />

**Verified syntax on https://yamltools.dev/en/syntax-checker;**

<img width="493" height="110" alt="image" src="https://github.com/user-attachments/assets/b98403fe-c1a9-49aa-aa73-f52e74bc428d" />

**CLI:** id

<img width="468" height="72" alt="image" src="https://github.com/user-attachments/assets/54676016-0023-4050-980c-9d99fa85e8bb" />

**Try logging in via browser:**

<img width="278" height="214" alt="image" src="https://github.com/user-attachments/assets/9344637e-3c6b-4e24-8e6d-c5546c4fb8b3" />

**Try to start docker:**

<img width="468" height="52" alt="image" src="https://github.com/user-attachments/assets/db68aaa7-0c49-4399-8b3b-11c2daf79a43" />

**Troubleshooting begins:** docker ps

<img width="468" height="109" alt="image" src="https://github.com/user-attachments/assets/bb95ea64-aaac-4684-a9e4-1a235dafc71c" />

**Trying to add ‘1000’ to the UID, GID area in the yml file:** 

<img width="297" height="46" alt="image" src="https://github.com/user-attachments/assets/176c3475-aea1-4c17-a130-b0f1ceef1f18" />

# Notes
- ‘echo’; means write
- Files with a dot before them are hidden; .env
- Every time Docker is changed it will have new password.
- **Lists all files:** ls -a
- **Tried adding to CLI:**
-  echo "UID=$(id -u)" >> .env
-  echo "GID=$(id -g)" >> .env
- **Then:** 
- docker compose up 
- 'd' to detach

**Returns:**
<img width="468" height="252" alt="image" src="https://github.com/user-attachments/assets/9b950ce7-cb39-4f85-b60a-ed0f5fc18452" />

**CLI:** ls -a

<img width="253" height="42" alt="image" src="https://github.com/user-attachments/assets/7a2ba969-2ca5-41e9-92fb-90edebe2974c" />

**CLI:** cat .env (not good, should only be one set)

<img width="199" height="69" alt="image" src="https://github.com/user-attachments/assets/459ab14a-53a8-4aa8-b420-16753ca75ca1" />

Checked the yml file, only listed once:

<img width="382" height="138" alt="image" src="https://github.com/user-attachments/assets/71973419-df8e-4ecc-8755-8bb3c6fc54a2" />

Try changing the ownership of the folders because or possible ‘root’ issue pasting in:

<img width="468" height="66" alt="image" src="https://github.com/user-attachments/assets/b451e231-54bb-4e92-a0f0-3599dbe6fe13" />

**Returns:**

<img width="349" height="71" alt="image" src="https://github.com/user-attachments/assets/28449021-7d0a-4bfc-be27-6c3c04c48f91" />

**Maybe issues still in the .yml file, shut down docker:**

<img width="251" height="23" alt="image" src="https://github.com/user-attachments/assets/4bd6c188-4b8f-4f36-bdbd-7568ab508f5b" />

<img width="295" height="50" alt="image" src="https://github.com/user-attachments/assets/0a2108ae-62c2-4061-b729-3bc5bccb286a" />

**Try logging in again:**

<img width="193" height="253" alt="image" src="https://github.com/user-attachments/assets/8f41ad1b-a01d-4733-b234-e28b16852939" />

**Checking Proxies servers (not on):**

<img width="319" height="195" alt="image" src="https://github.com/user-attachments/assets/05d30712-0ef9-4b74-8517-261ef1b2235e" />

**‘cat .env’ returns 4 sets now instead of 3:**

<img width="176" height="73" alt="image" src="https://github.com/user-attachments/assets/f203a210-1b82-48e5-9969-cd14ac310bd2" />

**Tried to fix the GUD, IUD output:**

<img width="298" height="258" alt="image" src="https://github.com/user-attachments/assets/9d9290d8-78b9-42bf-b66e-bd20efd8f602" />

**Tried using this advice;**

<img width="468" height="72" alt="image" src="https://github.com/user-attachments/assets/fca3d980-1da4-498b-9dd2-c652d5a07121" />

**Returns: (It says listening on port 80 for some reason.)**

<img width="373" height="226" alt="image" src="https://github.com/user-attachments/assets/e2318ad4-60c2-4a0c-82b0-7d2dfc2df268" />

**CLI:** ls -ln

<img width="268" height="55" alt="image" src="https://github.com/user-attachments/assets/949d7ff5-df4f-4e3d-a702-e5575a0d1bd6" />

**CLI:** ls -ln ./config

<img width="305" height="35" alt="image" src="https://github.com/user-attachments/assets/ee5448af-562b-45bc-aeb7-583f7fd11c7a" />

**CLI:** docker compose config

<img width="247" height="274" alt="image" src="https://github.com/user-attachments/assets/58c616ca-143a-4c1c-a1e7-e8cbeab16e37" />

**CLI:**

<img width="368" height="45" alt="image" src="https://github.com/user-attachments/assets/711cbc47-1ccd-411b-b5e8-7cb8fbb73a96" />

**Updated .yml file:**

<img width="225" height="103" alt="image" src="https://github.com/user-attachments/assets/d52ee5fc-0a8e-441f-99f0-c76e180ca040" />

**CLI:** docker compose up

<img width="335" height="262" alt="image" src="https://github.com/user-attachments/assets/ae7401e3-9b4d-47eb-a4bd-59a820ca04f2" />

**Enter ChatGPT:**

<img width="345" height="156" alt="image" src="https://github.com/user-attachments/assets/294f7559-dbab-475f-ae83-3a521930a511" />

**PW Generated:**

<img width="328" height="183" alt="image" src="https://github.com/user-attachments/assets/d96d8b77-2ed3-4ecd-b6e1-356d67c96bfb" />

**Logging into filebrowser:**

<img width="254" height="334" alt="image" src="https://github.com/user-attachments/assets/f3cbbe1c-a5c3-44dc-95ce-9ffea7ab7626" />

**Creds:** admin, random new pw from the docker compose up field.

<img width="468" height="229" alt="image" src="https://github.com/user-attachments/assets/5ef98b94-3473-434c-9e5e-cb433e28b354" />



