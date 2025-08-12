# Capture-and-Analyze-Network-Traffic-Using-Wireshark



<img width="1000" height="700" alt="Image" src="https://github.com/user-attachments/assets/a845dec4-be7f-453d-b158-dbeb2d0348c6" />

"Use Wireshark to capture and analyze network traffic. Monitor live data, filter packets, inspect protocols (HTTP, DNS, TCP/IP), and detect anomalies for troubleshooting and security analysis."


******************

1. Setup & Capture

2. 
          Download & install Wireshark from  here -->  https://www.wireshark.org/download.html

   then we can open the  tool  like this two methods which  one you  can more easy  use  it

       1 First cli  mod
         command : wireshark (then  hit the enter)
        
   <img width="1000" height="300" alt="Image" src="https://github.com/user-attachments/assets/8bf1d6a3-e886-4e87-80e9-4fbd48c3eb5f" />

 
   You can see wireshark is  open in gui


   Next we  can opthe tool  directly like  this


   
<img width="1000" height="500" alt="Image" src="https://github.com/user-attachments/assets/82302096-7954-40e0-8643-bc6a0bd35e20" />

------------------------------------------------------------------------------------------------------------------
   OK eveerything  is set  we  can go to Capture and Analyze Network-Traffic

   
    Select the correct network interface wlan0,eth0 (Wi-Fi/Ethernet).

    Start capturing traffic (click "Start" or press Ctrl+E).
we  got something like this !!!




<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/70f7bf1e-de8f-43af-a83d-583a7cbd439c" />





you  can see  some numbers  and ips  and some name  this  is  called  packet     PACKET ????

    What is a packet?
    In networking, a packet is a small segment of a larger message. Data sent over computer networks*, such as the Internet, is divided into packets. These packets are then recombined by the         computer or device that receives them.
    a packet (or network packet) is a fundamental unit of data transmitted over a network. It consists of two main parts

    1 Header: Contains control information like:

    Source and Destination IP/MAC addresses (who sent it and where it's going).
    Protocol type (e.g., TCP, UDP, HTTP, DNS).
    Port numbers (to identify applications/services).
    Sequence numbers, flags, and other metadata (for reliability/ordering).

    
    2 Payload: The actual data being sent (e.g., a webpage, email, or file content).


    Why Packets Matter
    Troubleshooting: Identify failed connections or slow responses.
    Security: Detect malicious traffic (e.g., port scans, malware C2).
    Forensics: Reconstruct files/emails from captured data.....


ok  we  can Analyze Network-Traffic

first  i  use  extract only http/https/tls packet 

      i use  this  filters  
      http.request.method --> http. only(for request)
      http2  or  tcp.port == 443 --> https(443 https )
      tlc  -->tlc 


  ***HTTP***

  <img width="1899" height="951" alt="Image" src="https://github.com/user-attachments/assets/63240a2b-ff2c-41e8-949e-7306f85a0e58" />


  ***HTTPS***

<img width="1900" height="954" alt="Image" src="https://github.com/user-attachments/assets/b8b2f297-02d3-456f-89af-365ec37cd8db" />

  ***tlc***

  <img width="1897" height="957" alt="Image" src="https://github.com/user-attachments/assets/29ec1f7f-3cfc-47a7-b0c4-d0622ebfc44a" />   


 We can see information about TLS — it’s a TCP-connected protocol.
The version is TLS 1.3, and the source IP & destination IP, as well as the MAC addresses, are also visible.



-----------------------------------------------------------------------


NEXT we  use  tcp filter 

     you  can use  this  in the  wirshark  add filter area (apply as a dispay filter )

     tcp ---> see the  tcp connection 
     tcp.port == 443 --> filtered only httpds used tcp connection
     tcp.port == 80 -->  use  this  for  http used tcp  connection
     
<img width="1902" height="947" alt="Image" src="https://github.com/user-attachments/assets/b23fdb28-9bbe-420f-98db-1f89caf070f4" />
     



why we can do  ICMP          


      add icmp in apply filter 


  <img width="1910" height="958" alt="Image" src="https://github.com/user-attachments/assets/edae0ea9-1c1b-49c2-a607-1f22eb68353d" />    




i try DNS

     dns --> apply as  filter       

<img width="1914" height="1024" alt="Image" src="https://github.com/user-attachments/assets/a047b88b-c884-4632-9e89-e1766bcd1c39" />



    
    I used the DNS filter in wirshark to view the domain names I had browsed, by extracting DNS query packets from the capture file.






finaly i check  the arp  request 

    apply filter arp 


  <img width="1912" height="945" alt="Image" src="https://github.com/user-attachments/assets/1a37d50c-ded4-4faa-86d2-1abf11ce19f4" />  




this  wirshark is a powerfull tool to  packet analyzing 

<img width="1400" height="836" alt="Image" src="https://github.com/user-attachments/assets/925cf2f3-e975-4ec9-bb68-2b1595c64b9e" />



