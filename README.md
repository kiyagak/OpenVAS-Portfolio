# OpenVAS-Portfolio
A portfolio showcasing my use of OpenVAS, a vulnerability scanner that users community and commercial threat feeds to identify vulnerabilities within systems and networks.  

# Installation Steps

I installed OpenVAS on Kali Linux, a Debian-based Linux distribution which includes OpenVAS in its official repositories.  

Update your system packages:

    sudo apt update
    sudo apt upgrade -y
    sudo apt dist-upgrade -y

Make sure firewall ports are not closed so the installation goes smoothly.  Then install OpenVAS:
    
    sudo apt install openvas

Initialize and set up OpenVAS with:
    
    sudo gvm-setup

Check the setup status:
    
    sudo gvm-check-setup

# Change the OpenVAS Admin Password

Open the Terminal to run the following commands.  

Stop the GVM service:

        sudo gvm-stop

Change the OpenVAS admin password:

    sudo runuser -u _gvm -- gvmd --user=admin --new-password=NEW_PASSWORD

# Access and Log into OpenVAS

Start OpenVAS:

    sudo gvm-start

Access the OpenVAS web interface with the default "admin" user and password either generated during setup or the one you changed it to.

    https://localhost:9392
or
    
    https://127.0.0.1:9392

# OpenVAS Threat Feed Synchronization

Upon login you will see a message saying "Feed is currently syncing."  The first OpenVAS feed synchronization after first installation typically takes several hours, depending on the performance of the host system and network speed. It downloads and loads several gigabytes of data into databases. It can take roughly two hours or more in common setups. While this is happening, the scanner may not yet be ready to run scans because it is still downloading and processing vulnerability test data and other community and commercial security threat feeds.

<img width="1382" height="443" alt="image" src="https://github.com/user-attachments/assets/c39cef01-288c-4651-a508-e99dfb220d41" />

You can view the feed status within OpenVAS using these steps:

1. In the left pane under Dashboards click **Administration**.  
2. Click **Feed Status**.
3. You will be able to run scans once all feeds are **Current**.  

<img width="1383" height="714" alt="image" src="https://github.com/user-attachments/assets/0683c9e6-7fa4-49d3-ab68-4963d994f5a6" />

# Run an Immediate Scan

You can run an immediate scan of your desired target using these steps:

1. In the left pane under Dashboards click **Scans**.
2. Click **Tasks**.
3. Click the **task wizard** at the top of the window by clicking the **black magic wand** beside the encircled question mark.  

<img width="1385" height="831" alt="image" src="https://github.com/user-attachments/assets/c3eab72e-003a-4931-9aa0-d043813c081b" />



