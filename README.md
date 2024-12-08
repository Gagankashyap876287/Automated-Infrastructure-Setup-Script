# Automated Infrastructure Setup Script for Windows
# Overview
This repository contains a PowerShell script designed to automate the setup of a basic infrastructure environment. The script deploys a Dockerized Nginx server, configures necessary networking settings, and adjusts Windows Firewall rules to allow seamless traffic.  
# Features
- Automated Setup: The script automates the entire process of setting up a Dockerized Nginx server, firewall configuration, and network setup.
- Docker Installation: Installs Docker Desktop automatically if not already installed.
- Nginx Deployment: Deploys the Nginx container on a user-specified port (default: 8090).
- Firewall Configuration: Configures Windows Firewall to allow inbound traffic on the specified port.
- Customizability: Supports changing the default port or serving custom HTML files via Nginx.


