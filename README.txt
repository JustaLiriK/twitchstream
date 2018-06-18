A Simple bash script to stream
from a Dazzle dvc100 graber thanks
v4l2 and avconv from libav and a raspberry pi.
The settings are the best i found for this device
and suitable video quality for retrogaming. 
First steps :
install libav-tools 
   sudo apt-get install libav-tools
allow the video4linux2 module 
   edit /boot/config.txt 
   and add the line :
   dtparam=v4l2=1
load v4l2 module (is it really necesserary with raspbian jessie?)
   sudo modprobe bcm2835-v4l2
   sudo reboot
Then plug in your dvc100 and tcheck if available :
   ls /dev/ | grep video 
output of the comand should be :
   video0 (single device connected)
if you have a webcam connected you should see at least
   video0 and video1 , first guess is the dvc100 is /dev/video1
Start wtreaming:  
   ./twitchstream (5 sec before it appears online)
Stop Streaming :
   CTRL+C 