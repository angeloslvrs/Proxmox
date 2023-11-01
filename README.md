# Proxmox
# Mounting SMB Share (https://support.zadarastorage.com/hc/en-us/articles/213024986-How-to-Mount-a-SMB-Share-in-Ubuntu)
1. sudo apt-get install cifs-utils
2. sudo mkdir /mnt/"ur share name"
3. sudo mount -t cifs -o user="user on smb share" //"ip"/"smb folder" /mnt/"ur share name"
4. sudo nano etc/fstab
5. //"ip"/"share" /mnt/"ur share name" cifs user="user on smb share",password="password",uid="user on machine",users 0 0

# Fixing Realtek RT8111 drivers
https://medium.com/@pattapongj/how-to-fix-network-issues-after-upgrading-proxmox-from-7-to-8-and-encountering-the-r8169-error-d2e322cc26ed

# Proxmox Scripts
https://tteck.github.io/Proxmox/

# Vaultwarden-alpine
Control if users can create an account
- nano /etc/conf.d/vaultwarden

# Migration
https://www.youtube.com/watch?v=E60_FC967YE

# Removing Temporary Cluster (from Migration)
https://pve.proxmox.com/wiki/Cluster_Manager
First, stop the corosync and pve-cluster services on the node:

systemctl stop pve-cluster
systemctl stop corosync
Start the cluster file system again in local mode:

pmxcfs -l
Delete the corosync configuration files:

rm /etc/pve/corosync.conf
rm -r /etc/corosync/*
You can now start the file system again as a normal service:

killall pmxcfs
systemctl start pve-cluster
The node is now separated from the cluster. You can deleted it from any remaining node of the cluster with:

pvecm delnode oldnode
If the command fails due to a loss of quorum in the remaining node, you can set the expected votes to 1 as a workaround:

pvecm expected 1
And then repeat the pvecm delnode command.

Now switch back to the separated node and delete all the remaining cluster files on it. This ensures that the node can be added to another cluster again without problems.

rm /var/lib/corosync/*
