# Sliver C2

* This is not a guide; this is simply a record of what I have done. If you want guides, you can use these links: 
* https://sliver.sh/docs or https://dominicbreuker.com/post/learning_sliver_c2_01_installation/


## New setup I have been using for my Sliver C2 attack VPS for my SOC homelab

- I have been using Sliver locally and have not yet configured "Multiplayer mode". Today, I decided to tackle this and configure my setup. I am still working out a few things that are giving me some issues, mainly with DNS, but I wanted to post what I have done so far.

- This configuration is utilizing the free tier AWS account. I am using a VPS Lightsale server that is configured for free and a free EC2 instance to be used as the vulnerable client that is off-network.

- If you don't want to use a VPS, you can use a Linux-based EC2 instance, but they are very slow on the free tier in AWS. However, you can use Azure, which is a lot faster. I like the headless server, though, and it's pretty quick with how little resources it has. Also, you get a static public IP if you want to use it.

### VPS Lightsale instance 

- I am using this VPS because it's free and very quick to spin up, and you get one free static public IP. So, if you want to spin and trash the VPS server without having to generate new beacons and implants, this is the way to go.
- I am using a bare-bones Debian server (OS ONLY) ![image](https://github.com/user-attachments/assets/27acbcec-452c-4924-90c2-72ecf4f87a5e) This is a very cheap instance even if you want to pay for it. I personally would recommend the $12 instance because of the higher RAM. The implants take about 2 minutes to generate compared to my local machine with 24 gigs of RAM generating implants instantly.
- After starting up the instance, these are the following things I did to get Sliver running:
- `apt update` / `upgrade`
    
- Installed Sliver with the one-liner provided from the Sliver docs: `curl https://sliver.sh/install|sudo bash`. Sliver did not enable in my `systemctl`, so I had to run `systemctl enable sliver` and then `systemctl start sliver`. If you don't do this, then you will need to go into the Sliver server and run the multiplayer command to have the server listen on the default port 31337. But once you exit the server, it will disconnect all connected operators.

- The only other programs I installed on the VPS server were TMUX and nginx. You could technically install all of your pentesting tools onto the VPS, but I wanted to keep this one strictly for Sliver, since the VPS has limited resources for the free tiers.

- The reason I installed nginx was to host files that can be downloaded using a domain I own. I can redirect my domain to the public IP and host files from it, doing this just to add another layer of realism. An easier way to do this without a domain and without nginx is just by spinning up an HTTP server with Python: `python3 -m http.server 8080`. I'm using this port just because I have Sliver listening on port 80 for implant callbacks.

- You will also have to open some ports on your VPS instance in order to get these services out to the public web: 
            ![image](https://github.com/user-attachments/assets/dac608ba-a019-4c1e-a3d1-2d5648d50224)

- After doing all of this, I created an operator on my Sliver VPS, saved the config file, then hosted the file through nginx, and downloaded it onto my local PC, then running `sliver-client import file` to import the operator onto my local Sliver client.

   ![image](https://github.com/user-attachments/assets/1340ff5a-b96f-46ca-91f6-49f51161ba98)
   ![image](https://github.com/user-attachments/assets/dc0eed9d-aa50-4b5d-98b1-f411ca994ab6)
   ![image](https://github.com/user-attachments/assets/61043725-d0cf-4c36-8c24-de5f0c7b27dc)

- I am connected to the Sliver server and able to see all local implants and sessions from my Sliver server in the VPS.

![image](https://github.com/user-attachments/assets/cb105e25-f3b9-4186-891b-b1f934ab88d5)


