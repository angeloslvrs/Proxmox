# Proxmox
# Mounting SMB Share (https://support.zadarastorage.com/hc/en-us/articles/213024986-How-to-Mount-a-SMB-Share-in-Ubuntu)
1. sudo apt-get install cifs-utils
2. sudo mkdir /mnt/"ur share name"
3. sudo mount -t cifs -o user="user on smb share" //"ip"/"smb folder" /mnt/"ur share name"
4. sudo nano etc/fstab
   4.1 //"ip"/"share" /mnt/"ur share name" cifs user="user on smb share",password="password" 0 0

# Proxmox Scripts
https://tteck.github.io/Proxmox/

# Vaultwarden
Control if users can create an account
- nano /etc/conf.d/vaultwarden

