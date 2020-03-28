# utorrent-linux
instalar utorrent no linux

```sh
#!/bin/bash

# País: Brasil
# Author:  Heuder Rodrigues de Sena
# E-mail: programadorwebti@gmail.com
# Telegram: @Heuderrodriguesdesena
# Phone: +5561993029884

sudo apt-get upgrade
sudo apt-get install libssl1.0.0 libssl-dev
wget wget http://download.ap.bittorrent.com/track/beta/endpoint/utserver/os/linux-x64-ubuntu-13-04 -O utserver.tar.gz
sudo tar -zxvf utserver.tar.gz -C /opt/
sudo chmod 777 /opt/utorrent-server-alpha-v3_3/
sudo ln -s /opt/utorrent-server-alpha-v3_3/utserver /usr/local/bin
utserver -settingspath /opt/utorrent-server-alpha-v3_3/ &


cd /etc/init.d
touch utorrent.sh
chmod 777 utorrent.sh
echo "#!/bin/bash" >> utorrent.sh
echo "utserver -settingspath /opt/utorrent-server-alpha-v3_3/ &" >> utorrent.sh
update-rc.d utorrent.sh defaults
chmod 777 utorrent.sh

```
