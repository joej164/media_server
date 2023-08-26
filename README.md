# media_server
This is my script for setting up the server and installing Jellyfin as a container on an Ubuntu 22.04 Base Server image.
I also added an external WD Easystore drive to store all the media.

It creates the Media and Shows folder in the external hard drive and mounts those directories into the Jellyfin Container.

Once loaded just navigate to http://<server name or ip>:8096 and configure the server if needed.  The config directory is also on the easystore drive, so may not need to configure anything either.

# Prereqs
- Install Ubuntu 22.04 on the server
- Connect the external drive to a USB port
- Run `fdisk -l` to get the mount point the external drive and update the media_server.yml file if necessary
- Pick a new SMB password for use as an extravar
- Install tailscale role `ansible-galaxy install artis3n.tailscale`

## Commands
- `ansible-inventory --list -y -i hosts`
- `ansible-playbook media_server.yml -k -i hosts --ask-become-pass --extra-vars "smbpass=<<smbpasshere>>"`


## Post Ansible Run
- Log into the server and set up tailscale
    - SSH to server
    - Log into Tailscale on a web browsers on the Ansible control machine
    - Type `tailscale up`
    - Copy the url into another tab on the web browser to authenticate the server
- Note the PiHole password for later use