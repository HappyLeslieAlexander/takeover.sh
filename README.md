```bash
cd ~
wget https://github.com/HappyLeslieAlexander/takeover.sh/releases/download/Alpine/alpine-rescue.tar.gz
sudo -i
apt update; apt install busybox git build-essential -y
mkdir /takeover
mount -t tmpfs tmpfs /takeover -o size=300M
cd /takeover
wget https://cdn.jsdelivr.net/gh/HappyLeslieAlexander/takeover.sh/takeover.sh
wget https://cdn.jsdelivr.net/gh/HappyLeslieAlexander/takeover.sh/fakeinit.c
wget https://cdn.jsdelivr.net/gh/HappyLeslieAlexander/takeover.sh/busybox
chmod +x busybox
tar -xpvzf ~/alpine-rescue.tar.gz -C /takeover
gcc -static fakeinit.c -o fakeinit
sh takeover.sh
# Follow instructions
exec /bin/sh
# ssh -p 80 root@server.hostname
# Enjoy
```
