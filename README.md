# RaspiCam-MJPEG
A Web Streamer for the Raspberry Pi with Motion JPEG and HTTP Web Sockets

# Hardware Required :-
1. Raspberry Pi B+/2 Board

2. Raspberry Pi Camera

# First Install Node.js on the Raspberry Pi Board :-

Download Node.js source :-

### Raspberry Pi Model A, B, B+ and Compute Module

` wget https://nodejs.org/dist/v4.0.0/node-v4.0.0-linux-armv6l.tar.gz 
tar -xvf node-v4.0.0-linux-armv6l.tar.gz 
cd node-v4.0.0-linux-armv6l `

### Raspberry Pi 2 Model B 

` wget https://nodejs.org/dist/v4.0.0/node-v4.0.0-linux-armv7l.tar.gz 
tar -xvf node-v4.0.0-linux-armv7l.tar.gz 
cd node-v4.0.0-linux-armv7l `

###Copy to /usr/local
` sudo cp -R * /usr/local/ `

That's it! To check Node.js is properly installed and you have the right version, run the command node -v
This should print the version of Node.js you have installed on your Raspberry Pi.

# MJPEG Details :-
### Understanding MJPEG

Based on what I have googled and understood, there is no straight forward way of streaming the live video from the camera module to a web browser.

After going through a few similar solutions, I kind of sort of decided that MJPEGs are the way to go when dealing with Live streaming from the Pi.

MJPEG is Motion JPEG.For more details visit :- [this](https://www.youtube.com/watch?v=jculwCLhn8Y)
In this post we are not really using MJPEG from a technology standpoint, but we are using a similar principle.

The idea is that we keep clicking pictures using the camera say for every 100ms and then save it to the same file. And then we keep sending the same image to the client as it changes every time.

# The System Build
So, the idea is very simple, we will have a web server setup on the Pi. When we get a request to start the stream, we will trigger a child process in node that will start capturing the picture, once for every 100ms.

Then we have a file watcher on that image file and whenever the file changes, we trigger the client to load the new image.

We are using Web Sockets to emit and act on the events accordingly.

Now, login to your pi via ssh – terminal/putty. As soon as you ssh into pi, you will be landing inside the /home/pi folder.Run
#### Cloning this repository onto Edison

To install git:

    opkg install git

Then clone this repository using `git clone <git repo URL>`.
Navigate to the folder :-

`cd node_programs`

Step inside the folder liveStreaming. Run

`cd liveStreaming`

Note : You can run multiple commands separated by a &&.

First we will initialize a new node project here. Run

`npm init`

Fill it up as applicable.

Now, we will install express and socket.io modules on our pi. Run

`npm install express socket.io --save`

Once they are installed, Run :-

`ls`

This will give give you a list of files in the folder you are currently in. 

Here you can find a file `index.js`



# Alternatives
This is really not the best of solutions, but it kind of gets the job done.
For more details go to my GitHub Account Page : [ShubhamCpp](https://github.com/ShubhamCpp)
Here I have explored various other technologies, these include :-

1. MJPEG (Discussed here) using HTTP Web Sockets

2. FFMPEG using HTTP Web Sockets

3. Gstreamer (Best in my opinion)

4. UV4L and UV4L-Raspicam

I got the best experience with Gstreamer for my application, however you may feel that something else works out for you better. This will depend on the application you are developing. I'll be happy if anyone of the following help you out in some way. :)
