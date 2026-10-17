# Lab 3 - Docker

## Resources

https://docs.docker.com/engine/install/ubuntu

## Initial Steps Taken

- Unable to get IP, returns 127.0.0.1
- Returns ‘not connected to the network’
- Tried to sudo apt update
- Returned; Warning: Failed to fetch http://us.archive.ubuntu.com ….. Looks like 4 files total
- Determined that WiFi doesn’t connect. Connected Ethernet cable & is working
- Ubuntu -lab is updated.
- ip a returns same IP as before
- ssh from Host terminal to VM with: ssh labuser@192.168.0.79 is successful.
- install Docker from: https://docs.docker.com/engine/install/ubuntu;
<img width="647" height="355" alt="Screenshot 2026-08-04 at 12 41 11 PM" src="https://github.com/user-attachments/assets/f24db13d-9eab-4bcd-97cb-eb698f5be9dd" />

- Upgrading

<img width="320" height="476" alt="image" src="https://github.com/user-attachments/assets/a167407a-3996-4294-990c-63b703f14520" />

- Install

<img width="649" height="37" alt="Screenshot 2026-08-04 at 12 44 55 PM" src="https://github.com/user-attachments/assets/b41714a8-4133-4f42-8e85-9ccf07386aff" />

- Packages are up to date.

<img width="339" height="154" alt="image" src="https://github.com/user-attachments/assets/806802a8-2a46-458f-934a-f08abc838684" />

- After installation verifying that Docker is running:

<img width="280" height="20" alt="Screenshot 2026-08-04 at 12 47 52 PM" src="https://github.com/user-attachments/assets/b9ce310e-7a46-4b3a-8f29-7db2a7d1b8be" />

- If Docker is not running, start it manually.

<img width="266" height="17" alt="Screenshot 2026-08-04 at 12 47 55 PM" src="https://github.com/user-attachments/assets/a1ab1cc0-dc97-4084-b261-94e0889fca2e" />

- Running

<img width="349" height="181" alt="image" src="https://github.com/user-attachments/assets/e477ce04-f7be-4ab3-9d26-75eda666769a" />

- q to exit status
- Verify that the installation is successful by running the hello-world image:

<img width="299" height="201" alt="image" src="https://github.com/user-attachments/assets/3cb52eec-2447-41d3-8b56-760e981f4dc4" />

- Pull NGINX;

<img width="468" height="244" alt="image" src="https://github.com/user-attachments/assets/da357121-c36f-400e-8a61-31cbabef920d" />

- cd

<img width="436" height="146" alt="image" src="https://github.com/user-attachments/assets/3d67d883-d318-487c-b8d9-ddb78177b730" />


- exit
- cli; docker run -d -p 8080:80 nginx

  <img width="468" height="63" alt="image" src="https://github.com/user-attachments/assets/7bb47afb-d1a6-43c1-8809-ac1e56141309" />

##  Diagnostic Steps:
1.	Check if port 8080 is in use: netstat -tulpn | grep :8080 (Linux) or
2.	lsof -i :8080 (macOS)
3.	Check if port 80 is in use: netstat -tulpn | grep :80
4.	If a conflict exists, stop the process or change the port mapping. 
Command netstat not found…

- Troubleshooting
- Restarted docker

<img width="356" height="375" alt="image" src="https://github.com/user-attachments/assets/792ca761-4f0d-4353-93da-bd06a33e6885" />

- Trying cli: docker run -d -p 8080:80 nginx & returns;

<img width="468" height="35" alt="image" src="https://github.com/user-attachments/assets/c5bd32e3-8793-4724-86a0-9ce283f317f2" />

- Tried with 'sudo' & was successful;

<img width="468" height="45" alt="image" src="https://github.com/user-attachments/assets/7324cc47-d94c-4a39-bf27-caaf23a4a676" />

- Typed IP into browser & can access the container through a port over the internet;

<img width="231" height="112" alt="image" src="https://github.com/user-attachments/assets/28d9cf2c-6094-457f-8722-c0f3ad1b5f76" />

<img width="468" height="76" alt="image" src="https://github.com/user-attachments/assets/b9c94b6f-7a03-4047-869d-5e174be98627" />

- Stopping Docker

<img width="468" height="114" alt="image" src="https://github.com/user-attachments/assets/92896644-06f3-42ae-82f6-8f7c96134f7f" />

<img width="111" height="124" alt="image" src="https://github.com/user-attachments/assets/35259c7e-e121-42cf-b6d1-780cb9228746" />

