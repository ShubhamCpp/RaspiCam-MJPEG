# RaspiCam-MJPEG
A Web Streamer for the Raspberry Pi with Motion JPEG and HTTP Web Sockets

Hardware Required :-
1. Raspberry Pi B+/2 Board
2. Raspberry Pi Camera

First Install Node.js on the Raspberry Pi Board :-

Download Node.js source
Raspberry Pi Model A, B, B+ and Compute Module 
wget https://nodejs.org/dist/v4.0.0/node-v4.0.0-linux-armv6l.tar.gz 
tar -xvf node-v4.0.0-linux-armv6l.tar.gz 
cd node-v4.0.0-linux-armv6l

Raspberry Pi 2 Model B 
wget https://nodejs.org/dist/v4.0.0/node-v4.0.0-linux-armv7l.tar.gz 
tar -xvf node-v4.0.0-linux-armv7l.tar.gz 
cd node-v4.0.0-linux-armv7l

Copy to /usr/local
sudo cp -R * /usr/local/

That's it! To check Node.js is properly installed and you have the right version, run the command node -v
This should print the version of Node.js you have installed on your Raspberry Pi.
