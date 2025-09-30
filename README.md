# OpenVAS-Portfolio
A portfolio showcasing my use of OpenVAS, a vulnerability scanner that users community and commercial threat feeds to identify vulnerabilities within systems and networks.  

# Installation Steps

I installed OpenVAS on Kali Linux, a Debian-based Linux distribution which includes OpenVAS in its official repositories.  

Update your system packages:

    sudo apt update
    sudo apt upgrade -y
    sudo apt dist-upgrade -y

**Make sure your network's firewall ports are open** for a **smooth installation**.  Then install OpenVAS:
    
    sudo apt install openvas

Initialize and set up OpenVAS with:
    
    sudo gvm-setup

Check the setup status:
    
    sudo gvm-check-setup

If there are any warnings or suggestions, follow the steps presented in the terminal to correct them.  

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
3. Click the **task wizard** at the top of the window by clicking the black **wand** beside the encircled question mark.  

<img width="1383" height="714" alt="image" src="https://github.com/user-attachments/assets/c7113dc3-fe72-4b93-8dbd-ab99dc9c2fde" />

4. In the **IP address or hostname** field enter your desired **target IP address**.
5. Click **Start Scan**.

<img width="553" height="643" alt="image" src="https://github.com/user-attachments/assets/50232b4c-e8d7-4be5-97e6-ad2031dd297f" />

**Scan durations** are usually between **30 minutes to several hours** depending on the environment and scan scope.  

## View the Report

Once the scan is done you can view the report to find information that includes the results, hosts, port information, applications, operating systems, CVEs, closed CVEs, TLS certificates, error messages, and user tags.  

<img width="1383" height="715" alt="image" src="https://github.com/user-attachments/assets/197b8c38-1e17-47bc-9c61-8de2bad613ef" />

The **Results** tab of the port will list the vulnerabilities found, with information about the vulnerability, severity, and the quality of detection (QoD).  



