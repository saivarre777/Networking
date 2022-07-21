# Networking
Notes
   -128 64 32 16 8 4 2 1
   -1   0   1 0  1 0 0 0
   -starting address -->network
   -end user address --> broadcast
-----------------------------------------------
   -192.168.0.98-----1100 0000.1010 1000.0000 0000.0110 0010-------
----------------------------------------------------------------------
   -192.168.4.237------->>>>1100 0000.1010 1000.0000 0100.1110 1101
   -255.255.255.0------->>>>1111 1111.1111 1111.1111 1111.0000 0000
-------------------------------------------------------------------------

   -192.168.4.0    --- 1100 0000.1010 1000.0000 0100.0000 0000  --------> network address
   -192.168.4.255  ---  1111 1111.1111 1111.1111 1111.0000 0000 ----> broadcast address
-------------------------
   -10.154.104.27 ---0000 1010.1001 1010.0110 1000.0001 1011 ----ip 
   -255.0.0.0    ----1111 1111.0000 0000.0000 0000.0000 0000  ---- class a 
-------------------------------------------------------------------
   -10.0.0.0   -->   0000 1010.0000 0000.0.0 ---> network (AND)
           --->   ----> broadcast---10.255.255.255
---------------------------------------------
 -class A -> 0-127--->255.0.0.0/8--->    0 1 1 1 1 1 1
-class B -> 128-191---->255.255.0.0/16--> 1 0 1 1 1 1 1 1
-class C -> 192-223-->255.255.255.0/32-mask representation-->1 1 0 1 1 1 1 1
-CLASS D -->  1 1 1 0 1 1 1 1

-----------------------------------------
-1100 0000.1010 1000.0000 0100.1111 1111--192.168.4.225

-----------------------
CIDR METHOD
---------------
-CLASSLESS INTER DOMAIN ROUTING/SUBNETTING---------/20
-IT IS BASED ON EUD USER

------------------------
-192.168.64.1/24---CLASSFUL--CLASSC
-BSNL--19+2=21---256-21=235

-24N,8H
-CHOOSE THE NEAREST VALUE OF SERIES (32)
-21<=32---(32-21=11)
-24N,11H
-8-11-->3
-8-3-->5H
-27N,5H
-1111 1111.1111 1111.1111 1111.1110 0000--255.255.255.224

-----------------------------------
PROTOCOLS
-1.TRANSMISSION CONTROL PROTOCOL (EX:HOTEL RESERVATION)

-------------------------------------
-gateway address--> the address which is connect


-r2------2 interface f0/0---40.0.0.0
                    f0/1---30.0.0.0
-conf t--global config terminal 
-ip dhcp pool pool1---dhcp server
-network     ---
-dnsl-server   ---
-default-router --
-lease days  ---
-----------------------------------------------------
-dhcp server (tcp) and dhcp client (udp for first discover)
-pool creation along with pool name
-add network addresss with mask
-create default gateway and assign the same gw address as dhcp server ip
-create lease time (day/hours/min)
-create binding by adding address exclusion range add ip address with server physical interface followed by same network address
-bind the dhcp with total pool by offering client ip service
----------------------------------------------------------------------------------
conf t
-ip dhcp 
-------------------
-SERVER TO SERVER TCP PORT 53
-LOCAL TO ROOT TCP
---------------
DNS STRATERGY (DOMAIN NAME SYSTEM)
---------------
CLIENT TO SERVER(SECONDARY SERVER/LOCAL NAME SERVER) UDP PORT NO 53
ROOT TO CLINET NO DIRECT CONNECTION
LOCAL NAME SERVER TO ROOT---TCP 53
VALIDATION TO CLINET NO DIRECT CONNECTION

AUTHORIZATION TO ROOT TCP 53
AUTHORIZATION TO LOCAL NAME SERVER TCP 53
------------------------------------------------
------------------------------------------------
RECORDS ARE VERSATILE ATTRIBUTES THAT SPIKES ONLY IN DNS SERVER

WHEN THE CLIENT PROVIDES INPUT AS ARECORD OF TYPE EG:URL THEN RECORD SIGNIFIES
CARRIER OF IPV4 ADDRESS THAT IS MAPPED WITH SERVERS DOMAIN ADDRESS (FOR DESTINATION)

PTR---------ITS ENABLED WHEN INTERACTION BETWEEN TWO SERVERS FOR VALIDATION 
------------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------------
putty ----client interface channel
mobexterm---->public assignment for server managed dns,os(linux/unix)

ssh,tcp,html

-Telnet is unicast agent that allocates resources and avoids traffic because of TCP
---------------------------
------------------------------
-smtp (simple mail transfer protocol)
-mua ---clinet activity
-msa----application programming and software (msa mutural for mua and mta this incooperates the essential procedures requested by client )
-mta----delivery agent
-mda-- 
-Mail Delivery Agent (MDA) stores the email (incoming email) received from MTA and waits for the user to accept it.

-mail delivery to the inbox/storage?---->MDA

-SMTP server after it receives QUIT command from the client?--->221
------------------------------------
------------------------------------
-ftp(file transfer protocol)

-ftp uses port no 20 (opened by server (parent/root) channel is data channel) and 21 (opened by clinet and thechannel is control channel)

-data channel---->type of tcp ack >cumulative
-control channel --->high secure channel >due to tunnel established via ssh port no 21


-There are two modes in which FTP can work- Active and Passive. 
-In Active mode, the client establishes the control channel and the server is responsible for establishing the data channel. 
-Many client devices today are not able to accept incoming connections from servers due to the firewall settings on the client side.
 -So, it is better if client establishes both the channels. This is the second mode- Passive mode.
 
