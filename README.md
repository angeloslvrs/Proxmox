# Proxmox
# Mounting SMB Share (https://support.zadarastorage.com/hc/en-us/articles/213024986-How-to-Mount-a-SMB-Share-in-Ubuntu)
1. sudo apt-get install cifs-utils
2. sudo mkdir /mnt/"ur share name"
3. sudo mount -t cifs -o user="user on smb share" //"ip"/"smb folder" /mnt/"ur share name"
4. sudo nano etc/fstab
5. //"ip"/"share" /mnt/"ur share name" cifs user="user on smb share",password="password" 0 0

# Fixing Realtek RT8111 drivers
https://medium.com/@pattapongj/how-to-fix-network-issues-after-upgrading-proxmox-from-7-to-8-and-encountering-the-r8169-error-d2e322cc26ed

# Proxmox Scripts
https://tteck.github.io/Proxmox/

# Vaultwarden-alpine
Control if users can create an account
- nano /etc/conf.d/vaultwarden

