# pyStream

## Summary

A simple RTSP streamer for the Ras Pi

## Camera configuration

To enable the CSI1 port on the RPi CM4, see https://wiki.seeedstudio.com/Dual-Gigabit-Ethernet-Carrier-Board-for-Raspberry-Pi-CM4/#dsi-and-csi-connectors-configuration

## Installing

Ras Pi OS "Bullseye" must be used, with Legacy camera support OFF.

This assumes that pyStream is located in /home/pi/pyStream

Run the following commands to install required packages:

sudo apt install -y python3-gst-1.0 libgstrtspserver-1.0-dev python3-pip
echo "PATH=\$PATH:~/.local/bin" >> ~/.profile
source ~/.profile
pip install -r requirements.txt --user

sudo cp pystream.service /etc/systemd/system
sudo systemctl enable pystream
sudo systemctl start pystream

## Running

Once running, the video streamer will be active at http://<CM4 IP>:5000, where settings can be configured.

The video streamer automatically saves settings and will restore them on reboot.
