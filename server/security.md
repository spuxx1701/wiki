# Set up firewall

```bash
sudo apt-get install ufw
sudo ufw default allow outgoing
sudo ufw default deny incoming
sudo ufw allow 20/tcp
sudo ufw allow 21/tcp
sudo ufw allow 80/tcp
sudo ufw allow 22/tcp
sudo ufw allow 443/tcp
sudo ufw allow 23/tcp
# Microk8s API server
sudo ufw allow 16443/tcp
```
