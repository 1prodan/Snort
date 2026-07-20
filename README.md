<h1>Sniffing with Snort</h1>

<h2>Description</h2>
Utilizing the many features of Snort to capture and analyze packets in a network, including the creation of rules to improve efficiency of analysis.

<br><br>
We begin by running a script to generate some ICMP and HTTP traffic to analyze with Snort.
<img src="https://i.imgur.com/Aa3Spbr.png" height="70%" width="70%"/>
<img src="https://i.imgur.com/LXQTPE4.png" height="70%" width="70%"/>

<br>
Snort is a rule based NIDS/NIPS which allows us to define and detect network activity. Snort has many different modes that can be used depending on the arguments used in the command. One of these is the sniffer mode which provides similar information to tcpdump. 

<br>
<img src="https://i.imgur.com/nPUa9Fu.png" height="70%" width="70%"/>
This is what sniffing the ICMP/HTTP traffic from the script looks like when using the verbose (-v) flag.

<br>
You can also choose to use the -l argument to create a log file that can be read later with -r. You can also open these files in tcpdump or wireshark for analysis as well. <br>
<img src="https://i.imgur.com/AVAbB7o.png" height="70%" width="70%"/>

<br>
Once you configure Snort, you can choose to run it in the background in its IDS/IPS mode. <br>
<img src="https://i.imgur.com/G8ZEjtz.png" height="70%" width="70%"/> 

<br>
You can investigate .pcap files with Snort to find different packet information or alerts based on the rules used in your config file.
<img src="https://i.imgur.com/vx0I8OW.png" height="70%" width="70%"/> <br>
<img src="https://i.imgur.com/FIbXlYo.png" height="70%" width="70%"/> 

<br>
Here we can see a rule created in order to alert the user when a specific IP ID is found in network traffic. The first part of the rule is the action, it can be alert, drop or reject. In this case I would like it to alert me when something happens. After is the protocol, in this case IP. Then, source and destination IPs and the direction of the flow of information, for this rule it is any and bidirectional. The tail end of the rule is the message when an action is complete, the reference (potentially a CVE), the rule id and the revision number for how many times the rule has been changed. You can get many different types of results depending on the information you need, such as individual packet information and how many times the alert went off.
<img src="https://i.imgur.com/1nF8gYX.png" height="70%" width="70%"/> <br>

<br>
Here are the results/summary of the IP ID rule (ID = 35369)
<img src="https://i.imgur.com/F8XvMoi.png" height="70%" width="70%"/> <br>

<br>
Rule for Syn flags and example packet result
<img src="https://i.imgur.com/0v0kVtd.png" height="70%" width="70%"/> <br>
<img src="https://i.imgur.com/HAx39dm.png" height="70%" width="70%"/> 

<br>
Rule for Push/ACK flags and alert results
<img src="https://i.imgur.com/llxGAfl.png" height="70%" width="70%"/> <br>
<img src="https://i.imgur.com/siNIs3z.png" height="70%" width="70%"/> 

