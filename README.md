# Automated Infrastructure Setup Script for Windows
# Overview
This repository contains a PowerShell script designed to automate the setup of a basic infrastructure environment. The script deploys a Dockerized Nginx server, configures necessary networking settings, and adjusts Windows Firewall rules to allow seamless traffic.  
# Features
- Automated Setup: The script automates the entire process of setting up a Dockerized Nginx server, firewall configuration, and network setup.
- Docker Installation: Installs Docker Desktop automatically if not already installed.
- Nginx Deployment: Deploys the Nginx container on a user-specified port (default: 8090).
- Firewall Configuration: Configures Windows Firewall to allow inbound traffic on the specified port.
- Customizability: Supports changing the default port or serving custom HTML files via Nginx.
 # Prerequisites
Ensure the following before running the script:
- Windows OS (Windows 10/11 recommended).
- PowerShell 5.1 or later.
- Administrator privileges to execute the script.
- Active Internet Connection to download Docker Desktop and Nginx.
# Setup Instructions
# Step 1: Clone the Repository
Open PowerShell and run the following commands to clone the repository and navigate to the project folder:  
git clone https://github.com/Gagankashyap876287/Automated-Infrastructure-Setup-Script.git
cd infrastructure-setup
# Step 2: Run the Script
Open PowerShell as Administrator.
Run the following command:
.\setup_infrastructure.ps1
# The script will:
- Check if Docker Desktop is installed. If not, it will automatically install Docker.
- Start Docker Desktop (if it's not already running).
- Pull the latest Nginx Docker image.
- Deploy an Nginx container on port 8090 (default).
- Add a Firewall rule to allow traffic on port 8090.
- Step 3: Access the Nginx Server
- After successful execution of the script, you can access the Nginx server:

**Local Access**: Open a browser and visit:  

http://localhost:8090  

**Remote Access**: Use the server's IP address to access the Nginx server:
http://<your-ip-address>:8090
# File Structure
- setup_infrastructure.ps1: The main PowerShell script that automates the infrastructure setup.
- README.md: Documentation providing detailed instructions on how to use the script.
# Troubleshooting
**Docker Desktop Issues**  

- Docker is not starting: Ensure Docker Desktop is properly installed and running. The script attempts to start Docker if it's not running.
- Restart Docker: If Docker fails to start after installation, manually restart Docker Desktop.
# Port Conflicts
- If port 8090 is in use, modify the script to use a different port by changing the $Port variable:

$Port = 8081  # New port number
# Firewall Issues
- Check if the firewall rule is active using the following command:

Get-NetFirewallRule | Where-Object DisplayName -eq "Allow Port 8090"
- If the rule is missing, add it manually:
New-NetFirewallRule -DisplayName "Allow Port 8090" -Direction Inbound -LocalPort 8090 -P



