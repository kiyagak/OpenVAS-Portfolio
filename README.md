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

Access the OpenVAS web interface with the default "admin" user and password generated during setup.

    https://localhost:9392
or
    
    https://127.0.0.1:9392

To change the OpenVAS admin password run the following command in the terminal:

    sudo runuser -u _gvm -- gvmd --user=admin --new-password=NEW_PASSWORD


