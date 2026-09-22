## I have practiced following NETWORKING COMMAND 

1.	ip addr – Displays the IP addresses and network interfaces configured on the system. 

2.	ping google.com – Checks whether the system can reach google.com over the network and measures the response time. 


3.	ping -c n google.com – Sends exactly n ping packets to google.com and then stops.
EX: ping -c 4 google.com sends 4 packets. 

4.	nslookup – Queries DNS to find the IP address associated with a domain name, or performs reverse DNS lookups. 
5.	curl http://example.com – Sends an HTTP request to the website and displays the response/content in the terminal. 

6.	curl https://example.com – Sends an HTTPS request to the website securely and displays the response/content in the terminal. 

7.	curl -I https://example.com – Sends a request and displays only the HTTP response headers, such as status code, content type, and server information.

8.	ss -tuln – Displays listening TCP and UDP network sockets with their port numbers and addresses. 
•	-t → TCP 
•	-u → UDP 
•	-l → Listening 
•	-n → Show numerical addresses/ports 

9.	netstat -tuln – Displays listening TCP and UDP network connections and their port numbers. It is an older alternative to ss. 

10.	traceroute google.com – Shows the network path (hops/routers) that packets take from your system to google.com, helping identify where network delays or connectivity problems may occur.

