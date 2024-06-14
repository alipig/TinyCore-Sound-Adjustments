# TinyCore Sound-Adjustments

## TinyCore Linux Based RPi tweaks for improved sound.
- For Debian based systems see [Debian Sound Tweaks](https://github.com/dynobot/Linux-Audio-Adjustments)

To improve the sound of the Raspberry Pi using TinyCore Linux several parameters can be adjusted. 

1) Improving the priority of the Audio threads
2) Change audio thread scheduling from 'other' to FIFO
3) Improving the latency of the Operating System with Kernel adjustments
4) Change Squeezelite priority and thread scheduling to FIFO

## Prerequisites
- SSH into PiCorePlayer
- see PiCorePlayer How-To for SSH instructions
- Run commands from home directory

## Install
1) wget https://github.com/dynobot/TinyCore-Sound-Adjustments/raw/master/install.sh
2) sudo chmod 755 install.sh
3) sudo ./install.sh


## Remove 
1) wget https://github.com/dynobot/TinyCore-Sound-Adjustments/raw/master/remove.sh
2) sudo chmod 755 remove.sh
3) sudo ./remove.sh



别优化这个

#Reduce Audio thread latency
chrt -f -p 43 $(pidof ksoftirqd/0)
chrt -f -p 43 $(pidof ksoftirqd/1)
chrt -f -p 43 $(pidof ksoftirqd/2)
chrt -f -p 43 $(pidof ksoftirqd/3)

你提高软中断优先级，可能会突然觉得耳目一新，当你听几个小时你就会觉得枯燥无味，声音没有感情，很干涩


