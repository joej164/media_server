# media_server

# Prereqs
- Install Ubuntu 22.04 on the server
- Connect the external drive to a USB port
- Run `fdisk -l` to get the mount point the external drive and update the media_server.yml file if necessary
- Pick a new SMB password for use as an extravar

## Commands
`ansible-inventory --list -y -i hosts`
`ansible-playbook media_server.yml -k -i hosts --ask-become-pass --extra-vars "smbpass=<<smbpasshere>>"`
