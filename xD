#!/bin/bash
# Install Dropbear
apt install dropbear -y
bash <(curl -s https://raw.githubusercontent.com/FN-Rerechan02/tools/refs/heads/main/dropbear.sh)
rm -f /etc/dropbear/dropbear_rsa_host_key
dropbearkey -t rsa -f /etc/dropbear/dropbear_rsa_host_key
rm -f /etc/dropbear/dropbear_dss_host_key
dropbearkey -t dss -f /etc/dropbear/dropbear_dss_host_key
rm -f /etc/dropbear/dropbear_ecdsa_host_key
dropbearkey -t ecdsa -f /etc/dropbear/dropbear_ecdsa_host_key
cd /etc/default
rm -f dropbear
wget -qO dropbear "https://raw.githubusercontent.com/88PanelSc/sc/main/files/dropbear"
echo "/bin/false" >> /etc/shells
echo "/usr/sbin/nologin" >> /etc/shells
echo -e "Dev @Rerechan02 Sponsored by @HarisTakiri" > /etc/issue.net
clear
systemctl daemon-reload
/etc/init.d/dropbear restart
clear
cd /root
rm -fr dropbear*

# Install SSH WebSocket
apt install python3 -y
cd /usr/local/bin
wget -qO proxy "https://raw.githubusercontent.com/88PanelSc/sc/main/biner/proxy"
chmod +x proxy
cd /etc/systemd/system
wget -qO ssh-ws.service "https://raw.githubusercontent.com/88PanelSc/sc/main/service/ssh-ws.service"
cd
systemctl daemon-reload
systemctl start ssh-ws.service
systemctl enable ssh-ws.service
