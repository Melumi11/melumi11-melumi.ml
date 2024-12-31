---
layout: post
title: Run a Minecraft Server Without Port Forwarding for Free – SSH Reverse Tunnel
date: 2024-12-31 11:59:00-0400
description: Free low ping hosting without SaaS like ngrok, playit.gg, or Hamachi
tags: games
categories: games
giscus_comments: true
related_posts: false
toc:
  beginning: true
---

### TL;DR

* You host the server but don't have to port forward
* Free
* Low latency
* Basically no data caps
* Players don't have to install anything (just connect to the ip in Minecraft)

Do you have a computer that can run Minecraft but can't port forward? You can use SSH reverse port forwarding with a free Virtual Private Server (VPS) from Oracle Cloud, Google Cloud, or AWS. By running a simple SSH command (`ssh -i key.pem -R external_port:localhost:internal_port user@vps_ip`), you can route traffic from your VPS’s public IP to your local server, allowing friends to connect from anywhere without configuring your router. This method avoids high ping and usage caps, making it a reliable, free alternative for hosting your server. When I want to play with my friends online, I can start my server normally, run the SSH command in another terminal window, and play Minecraft all on the same computer wherever and whenever I want.

### Introduction

If you’ve ever tried hosting your own Minecraft server but hit a roadblock with port forwarding, you’re not alone. Many people use tools like Hamachi, ngrok, zgrok, zerotier, remote.it, and playit.gg, but these all come with limitations like high ping/latency, usage/data caps, or require clients to download something. However, I recently discovered a better alternative using reverse port forwarding with a free VPS (Virtual Private Server) from providers like Oracle Cloud or AWS (Amazon Web Services).

In this guide, I’ll walk you through how to set up a Minecraft server using reverse port forwarding, step by step.

### What is Reverse Port Forwarding?

Reverse port forwarding allows you to route traffic from your VPS (which has a public IP) back to your local server through SSH. This method bypasses the need for traditional port forwarding on your home router. Think of it like a regular internet connection between your computer and a free private server (VPS) in the cloud. Instead of port forwarding your computer, the VPS is port forwarded and sends the data to your computer. The VPS is only sending Minecraft connections to your computer, so any free or cheap VPS should do. (Most free options have high enough bandwith caps and have enough locations that there should be no issue. You could also host a server directly on a VPS but then you'd need a more powerful one.)

Here’s the basic SSH command we’ll use:

`ssh -i key.pem -R external_port:localhost:internal_port user@vps_ip`

* key.pem: Your SSH key for the VPS.
* external_port: The port users will connect to on the VPS.
* internal_port: The port your Minecraft server is running on (usually 25565).
* user: The username for the VPS.
* vps_ip: The public IP address of the VPS.

### Set Up

Step 1: Choose a Free VPS
1.	Sign up for a Free VPS:
  - [Oracle Cloud Free Tier](https://www.oracle.com/cloud/free/): "10TB Outbound Data Transfer per month"
  - [AWS Free Trial](https://aws.amazon.com/free/): 12 months of Amazon EC2 per account. "100GB of data transfer out to the internet free each month"
  - [Google Cloud Free Tier](https://cloud.google.com/free/docs/free-cloud-features#compute): "1 GB of outbound data transfer per month"
  - (I have only tested AWS and Oracle Cloud (OCI). AWS had slightly better ping so that's what I've been using. For OCI free tier you can only expect to get AMD instances which are definitely enough. Upgrading from free tier to pay-as-you-go tier will get you Arm instances which are still free but way beefier. With Arm instances you could [run your server on those](https://www.reddit.com/r/admincraft/comments/qo78be/creating_a_minecraft_server_with_oracle_cloud/))

2.	Set up your VPS:
* Look up a reverse port forwarding guide for your VPS provider if the below doesn't work.
* Create an instance running a Linux distribution (e.g., Ubuntu 20.04).
* Configure SSH access and save the key file (I'm using a .pem file) to your computer.
* Set network settings:
  * In AWS this is set when creating an instance (or editing one). In Oracle Cloud (OCI) you need to add a security list to your instance's vcn subnet. You can click around in your VPS instance to find it.
  * Add an inbound rule to allow yourself to SSH into the server. Input the IP address range for the region you are using into the Source field or allow SSH from anywhere (0.0.0.0/0).
  * Add an inbound rule on your security group to allow TCP traffic from anywhere (0.0.0.0/0) for your Minecraft Server's port (default 25565).
    * Optional: For Bedrock edition players, add a rule that's the same but for UDP instead of TCP. If there are both Java and Bedrock players, add both.
  * This should look like `Source: 0.0.0.0/0; IP Protocol: TCP; Source Port Range: All; Destination Port Range: 25565`

Step 2: Set Up Your Minecraft Server
1.	Install Minecraft Server Locally
* I won't go over how to do this here, but I suggest including [Aikar's Flags](https://docs.papermc.io/paper/aikars-flags) if you haven't heard of them.

2.	Confirm it’s running on your internal port (default: 25565).
* You can test this by connecting to localhost in Minecraft (or localhost:port_num if not default).

Step 3: Configure Reverse Port Forwarding
1.	SSH into Your VPS:

`ssh -i key.pem user@vps_ip`

* Replace key.pem, user, and vps_ip with your actual values.

2.	Edit the sshd_config file on your VPS:
* Open the SSH configuration file:

`sudo nano /etc/ssh/sshd_config`

* Look for the line `#GatewayPorts no` and change it to `GatewayPorts yes`
* This ensures the VPS accepts connections from any external IP on the forwarded port.
* exit nano with `Ctrl+X` and `yes` to save

3. Restart the SSH service:

`sudo systemctl restart ssh`

4. Exit SSH:

`exit`

Step 4: Start Reverse Port Forwarding:
* Run the following command on your local machine, substituting `key.pem`, `external_port`, `internal_port`, `user`, and `vps_ip` with your own values:

`ssh -i key.pem -R external_port:localhost:internal_port user@vps_ip`

* This routes traffic from port external_port on the VPS to port internal_port on your local machine. (If your Minecraft Server is running on the default port but you want players to connect to port 36969, you could do `ssh -i key.pem -R 36969:localhost:25565 user@vps_ip`)

Step 5: Test Your Server
* Open Minecraft and connect to the server using the VPS public IP: vps_ip:port_num.

Additional Tips
* Make sure the SSH connection is active when trying to use the server
* Use ethernet for reduced ping and lag spikes
* Make sure you're only running one VPS at a time so you don't go over the free limits
* Consider changing the external port number and/or whitelist, especially if you're running an "offline" server. IP scanning bots may look for vulnerable ports and try to hack/grief your server
  * To choose a port number, you can look at [https://en.wikipedia.org/wiki/List_of_TCP_and_UDP_port_numbers](https://en.wikipedia.org/wiki/List_of_TCP_and_UDP_port_numbers) and choose a number that isn't commonly used.

By using reverse port forwarding and a free VPS, you can host a Minecraft server without port forwarding or third-party tools. It’s a cost-effective and low-latency solution that opens up new possibilities for your gaming experience!

<br>

Thanks for reading my post. Please leave a comment or reach out if you have any questions :)