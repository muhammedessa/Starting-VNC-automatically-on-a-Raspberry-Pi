# Starting-VNC-automatically-on-a-Raspberry-Pi


sudo nano /etc/init.d/tightvncserver

sudo chmod 755 /etc/init.d/tightvncserver
sudo update-rc.d tightvncserver defaults



#!/bin/sh
# /etc/init.d/tightvncserver

VNCUSER='pi'
case "$1" in
   start)
      su $VNCUSER -c '/usr/bin/tightvncserver :1'
      echo "Starting TightVNC Server for $VNCUSER "
      ;;
   stop)
      pkill Xtightvnc
      echo "TightVNC Server stopped"
      ;;
   *)
      echo "Usage: /etc/init.d/tightvncserver {start|stop}"
      exit 1
      ;;
esac
exit 0
