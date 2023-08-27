# Proxmox
# Mounting SMB Share (https://support.zadarastorage.com/hc/en-us/articles/213024986-How-to-Mount-a-SMB-Share-in-Ubuntu)
1. sudo apt-get install cifs-utils
2. sudo mkdir /mnt/"ur share name"
3. sudo mount -t cifs -o user="user on smb share" //"ip"/"smb folder" /mnt/"ur share name"

# Proxmox Scripts
https://tteck.github.io/Proxmox/
