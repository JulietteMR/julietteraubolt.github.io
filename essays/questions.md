---
layout: essay
type: essay
title: "Ask Smarter not Harder: Principles in Crafting Smart Questions"
# All dates must be YYYY-MM-DD format!
date: 2023-09-07
published: true
labels:
  - Questions
  - Answers
  - SuperUser
---

  There are countless ways to ask the same question. So, this raises the issue, how does one ask the question in the most effective way such that an answer is efficiently found. The following are two different situations stemming from the same issue. Elements of how to ask smart questions can be found through assessing the questions asked and the corresponding responses received. In this case study there seems to be an issue with a wifi card and monitor mode. The first question asks: 

```
“So I want to sniff WiFi traffic in my network (not the device wireshark is running on) while being connected so no decrypting with PSK. My WiFi card does support Monitor mode and Injections, however neither Wireshark or tshark let me use the Monitor mode. In Wireshark there's no checkbox to enable it.
Sniffing in monitor mode without being connected works fine, but I want to avoid the decrypring part for simplicity.
How do I get Wireshark to monitor anyways?”
```
This question is then responded with: 
```
“Not all cards support monitor mode while connected. You may have to use a different card. Please edit your question to include the details of your card and OS.”
```
The second question asks: 
```
“I was first using Kali 2020.3, and had to manually install my wireless driver (RTL8822BE). After that, monitor mode would work on it with the command sudo airmon-ng start wlan0. I decide to upgrade to Kali 2020.4 and it automatically had my wireless driver so connecting to WiFi wasn't a problem. The part that is the problem though is putting the WiFi card into monitor mode. I've tried sudo airmon-ng check kill to turn off the WiFi network and tried sudo airmon-ng start wlan0 to put the wireless card into monitor mode, but it automatically switches back to wlan0, and not wlan0mon. Even when I run the command sudo iwconfig, I get wlan0 and not wlan0mon. I don't ever see wlan0mon even when it's doing the command. I've tried reinstalling my WiFi driver and it doesn't change anything. I also have the problem of getting my internet back because when I use the command sudo airmon-ng check kill, it kills the WiFi process. I tried to use sudo service NetworkManager restart and it doesn't work (but the command itself works). The only way I am able to get WiFi back is to reboot.”
```
Which is then answered with: 
```
“I don't know if this still works for 2020.4 (since I'm on the weekly release of Kali), but I've found an answer.
To put your network card into monitor mode, first you have to stop the NetworkManager service (and for me doing sudo ifconfig wlan0 down will work to turn off the WiFi card for a second, then automatically turn itself back on even without using the command sudo ifconfig wlan0 down). To stop the NetworkManager run the command sudo service NetworkManager stop.
Secondly, you have to enable monitor mode. This can be done in 2 ways (maybe more but I don't know them), and that is running the command sudo airmon-ng start wlan0, or you can run the command sudo iwconfig wlan0 mode monitor (but this method doesn't seem to work as I've tried capturing packets and didn't get anything). To check if you are in monitor mode, run the command iwconfig (and even though it may not say wlan[#]mon it will say the mode it is in from the text Mode: "Your current mode".
Thirdly, to put your network card back into managed mode, run sudo ifconfig wlan0 down, sudo iwconfig wlan0 mode managed, then run sudo service NetworkManager start and it should work.”
```

  These questions and corresponding answers reveal the importance of asking questions that are precise, informative, and explicit. When the proper relevant information is provided and the main issue or goal is clear, the question is easier to specifically answer. Without these elements a question is too vague and the situation is unclear ultimately leading to a correspondingly vague unfocused answer if answered at all. 
  Assessing the first question it is apparent that the user is having issues with a wifi card and monitor mode while using wireshark. Though that is the extent of the information. This raises further questions such as what wifi card is being used, how exactly has the user attempted to use Wireshark, and is the question about sniffing in monitor mode in the first place or is it about decrypting? In this situation the question is neither precise or explicit and not very much background information is provided to form insight on what is going on. As such, we see there is no actual answer to this question, rather a counter question asking for more details. 
  Now contrasting with the second question, the situation is much more clear. Relevant details including operating system, hardware details, and specific commands used are put together to chronologically describe the issue and ultimately the question. In this case a precise question is asked with relevant, informative, and explicit details that productively contribute to a useful answer. Accordingly, the answer provided is specific with potential reasons behind the issues and correspondingly specific details and instructions on how to work through the problem. 
  It is important to be able to ask smart questions to more likely receive productive answers. What this means is providing background information to frame the situation, then explicitly asking the question, all while making sure to be precise. These elements contribute to smart questions that are easier to understand and easier to answer. Questions and problems are bound to arise in software development and by asking smart questions these problems can be worked through and learned from rather than becoming consuming roadblocks. 

<a href="https://superuser.com/questions/1613863/kali-linux-2020-4-not-going-into-monitor-mode">Smart Question</a>
<a href="https://superuser.com/questions/1655948/sniffing-with-wireshark-monitor-mode-not-available">Not So Smart Question</a>
