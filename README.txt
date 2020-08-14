                     	       		***Cisco QuickFetch Script v0.1***
                 	 	  This script only works on Cisco IOS (for now)
            	   	 List of supported vendors with Netmiko can be found here:
       		 https://github.com/ktbyers/netmiko/blob/master/netmiko/ssh_dispatcher.py#L87

-> ONLY TESTED ON PYTHON v3.8 <-

PURPOSE:

To make a convenient and easy way to grab interface information and command outputs on Cisco IOS devices
by providing it host IP, username, and pass.

HOW TO USE:

Method 1: Double click quickfetch.py (ensure using same python app as the one in your environment variables)
Method 2: Go to quickfetch.py path > python quickfetch.py XXX.XXX.XXX.XXX (where XXX.XXX.XXX.XXX is your hostname IP)
	  The script can takes the hostname IP as the first argument.

The script asks user for hostname, user, pass and logs into the Cisco device first via SSH and then Telnet.
If both fail, either hostname IP can't be reached or credentials are incorrect.


OPTIONS:

What would you like to fetch (choice: 1-5)?
1 - Get all ports with a packet count OVER 0 (1+ input packets)
2 - Get all ports with packet count of 0
3 - Get all connected ports (up/up)
4 - Get result from custom Cisco IOS command
5 - Exit

IMPORTANT!:
Option 1 currently ONLY checks for INPUT packets over 0, NOT BUM or OUTPUT packets.
If input packets are greater than 0, retain BUM and output packet for the interface BUT if input packets are 0
and BUM or output packets are GREATER THAN 0, the respective interface will be omitted.

Option 4 lets you input any Cisco IOS command and retrieve the results.

All results will be printed to console and inputted into a .log file as $hostname_$command


By: Owen Yuen (owen.yuen@lumentum.com, oweny@live.com)