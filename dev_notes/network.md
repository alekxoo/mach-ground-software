## Short Cuts 




## Fun trial and error 

>**Problem 1 Context:**

7/19/24: 

I wanted to find out if we can connect the camera to linux device directly without ethernet router/switch. Now I didn't know (I still don't know the detials) of how router works so there was a lot of question mark on if this is even possible. 

To validate that the conenction is stable I first connected camera and the linux and ran "ifconfig" where I saw an addition of an ethernet interface I haven't seen before. 

Now confusingly, it only had ipv6 address. I'm not used to ipv6 and only seen ipv4 (okay im getting lazy of typing now. I was excited to write this but nvm.) 

Speed run: So I found that I need to assign a ipv4 address. Now I didn't know what subnet the camera was on. The documentation said certain ip, so I followed that which started confusion (because that was the wrong subnet). Then I did lots of shooting the dark on... (i forgot what I did...) At the end what I did was used tcpdump to track the network traffic on the ethernet interface and found out about the ip address coming from the camera. Then I changed my camera's subnet to the same one then success! 

>**Solution 1: set linux devices subnet to be same as the camera subnet**

To change the ip of the ethernet permantently:
```markdown
cd /etc/netplan
sudo nano 01-network-manager-all.yaml

# Add this 
network:
  version: 2
  ethernets:
    enxa0cec87bc820:
      dhcp4: no
      addresses: [192.168.86.2/24]

sudo netplan apply
sudo reboot
```

Lesson: assume that whatever your assumption will work and narrow things down. Like why would the ethernet switch/router actually do anything? Wouldn't that be stupid if you can't directly connect the camera and linux device? This took like 3 hours to figure out. 