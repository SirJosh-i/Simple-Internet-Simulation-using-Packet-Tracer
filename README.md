# Internet Simulation & Packet Trace
![image](https://github.com/SirJosh-i/Simple-Internet-Simulation-using-Packet-Tracer/blob/master/Screenshots/Simple%20Internet%20-%20Cisco%20Model%20-%20Resized.png)
## 1. Install Packet Tracer
- Browse to: [Cisco_Download](https://www.computernetworkingnotes.com/ccna-study-guide/download-packet-tracer-for-windows-and-linux.html)
- Download the latest version and install it.
  ![image](https://github.com/SirJosh-i/Simple-Internet-Simulation-using-Packet-Tracer/assets/69949528/f02d720e-2b28-4fda-9a30-ace28bc0d47b)
  ### The Packet Tracer version: 8.2.2.0400
  ![image](https://github.com/SirJosh-i/Simple-Internet-Simulation-using-Packet-Tracer/assets/69949528/6211341c-f73d-416a-a9c5-23e96f0cced1)

## 2. Add the devices given below:
  - Two PC
  - One Switch(2960-24TT)
  - One Router(1941)
  - Two Server-PT
  - One HomeRouter or Wireless Router
  - One Laptop-PT
  ### Place them as: (Or whichever way, you're comfortable with):
  ![image](https://github.com/SirJosh-i/Simple-Internet-Simulation-using-Packet-Tracer/blob/master/Screenshots/Place_it_as_such%20-%20Cisco.png)
  
## 3. Connecting devices:
  ### Router, Switch and Home Router:
  - Choose **Connections** and Select: Copper Straight Through Wire.
  - Click on the Router, Select **GigabitEthernet0/0** and Connect it to the Switch **GigabitEthernet0/1**.
  - Again, Click on the Router, Select **GigabitEthernet0/1** and Connect it to the Home Router **GigabitEthernet0/1**.
    You can do either/or but, the router, switch and Home Router needs to be connected via GigabitEthernet.
    
  ### Switch, PC and Servers:
  - Switch and PC:
    - Choose **Connections** and Select: Copper Straight Through Wire.
    - Click on the Switch, Select **FastEthernet0/1** and Connect to PC1(In my case: Dell) - **FastEthernet0**.
    - Click on the Switch, Select **FastEthernet0/2** and Connect to PC1(In my case: Lenovo) - **FastEthernet0**.
      You can connect to any port of a Switch.
  - Switch and Servers:
    - Similarly, Connect to the servers using the ports available in Switch.

## 4. Configuring devices:
  ### PCs: Lenovo and Dell
  - Lenovo:
    - Click on your PC1 and Navigate to Desktop.
    - Head to Ip Configuration.
    ![image](https://github.com/SirJosh-i/Simple-Internet-Simulation-using-Packet-Tracer/blob/master/Screenshots/Lenovo%20-%20PC.png)
  - Dell:
    - Click on your PC1 and Navigate to Desktop.
    - Head to Ip Configuration.
    ![image](https://github.com/SirJosh-i/Simple-Internet-Simulation-using-Packet-Tracer/blob/master/Screenshots/Dell%20-%20PC.png)

  ### Laptop: MSI
  - Module Config: Configuring module such that the Laptop supports connection to both 2.4ghz wireless connection and Ethernet for LAN access.
  ![image](https://github.com/SirJosh-i/Simple-Internet-Simulation-using-Packet-Tracer/blob/master/Screenshots/Laptop%20-%20WPC300N_Module.png)
  - IPConfig:
    - Click on your Laptop and Navigate to Desktop.
    - Head to Ip Configuration
    ![image](https://github.com/SirJosh-i/Simple-Internet-Simulation-using-Packet-Tracer/blob/master/Screenshots/IP_Config%20-%20Laptop.png)

  ### Router
  - Click on your Router and Navigate to Config > Interface: **GigabitEthernet0/0**.
  ![image](https://github.com/SirJosh-i/Simple-Internet-Simulation-using-Packet-Tracer/blob/master/Screenshots/Router_Config%20-%20Switch_side%20-%20Gigabit0-0.png)
  - Click on your Router and Navigate to Config > Interface: **GigabitEthernet0/1**.
  ![image](https://github.com/SirJosh-i/Simple-Internet-Simulation-using-Packet-Tracer/blob/master/Screenshots/Router_Config%20-%20Wireless_Router_side-%20Gigabit0-1.png)

  ### Home Router
  - Click on your Home Router and Navigate to Config > Interface > Internet; Setting default Gateway:
  ![image](https://github.com/SirJosh-i/Simple-Internet-Simulation-using-Packet-Tracer/blob/master/Screenshots/Default_Gateway%20of%20Wireless_Router.png)
  - Also setup LAN under Interface:
  ![image](https://github.com/SirJosh-i/Simple-Internet-Simulation-using-Packet-Tracer/blob/master/Screenshots/IP_Config%20-%20Wireless_Router.png)

  ### Server1 - Web Server
  - IP Config: Navigate to Desktop:
  ![image](https://github.com/SirJosh-i/Simple-Internet-Simulation-using-Packet-Tracer/blob/master/Screenshots/Webserver_IP%20-%20Config.png)
  - HTTP Config: Navigate to Services > HTTP:
    - Edit the index.html file to your taste.
    ![image](https://github.com/SirJosh-i/Simple-Internet-Simulation-using-Packet-Tracer/blob/master/Screenshots/Webserver_Service%20-%20HTTP.png)

  ### Server2 - DNS
  - IP Config: Navigate to Desktop:
  ![image](https://github.com/SirJosh-i/Simple-Internet-Simulation-using-Packet-Tracer/blob/master/Screenshots/Server_DNS%20-%20IP_Config.png)
  - DNS Config: Navigate to Services > DNS:
    - Turn DNS Service to **ON**. 
    - Under Resource Records - DomainName: www.your_desired_name.com
    - Type of Record: Default
    - Address: Webserver's IPAddress.
    - Then, Click **Add**.
    ![image](https://github.com/SirJosh-i/Simple-Internet-Simulation-using-Packet-Tracer/blob/master/Screenshots/Server_DNS%20-%20Config.png)

## Simulation
  ### Connecting to the Webserver:
  - Click on any PC or a laptop.
  - Navigate to Desktop > Web Browser.
  - In the URL section, type in your Webserver's IPAddress and Click on **Go**; The index.html in Webserver will be displayed.
  ![image](https://github.com/SirJosh-i/Simple-Internet-Simulation-using-Packet-Tracer/blob/master/Screenshots/Webserver%20-%20Surf.png)

  ### Packet Trace:
  - On the bottom right - Click on Simulation.
  - A Simulation Panel will open on the right side.
  - On the edge, where the scroll lies; Resize the panel by dragging mouse to the left.
  - On the topbar_navigation, Select a packet(Referred in Network Layer)
  ![image](https://github.com/SirJosh-i/Simple-Internet-Simulation-using-Packet-Tracer/blob/master/Screenshots/Add-Simple-PDU.png)
  - Click on any PC or a Laptop and also select the endpoint i.e. To which device you want the selected packet to reach.
  - Now in the Simulation Panel, Click on Play.
  - The Simulation starts and if you have followed my directions step-by-step, the build will yield --> Successful
  - I sent the packet from Lenovo to MSI (PC to Laptop)
  ![image](https://github.com/SirJosh-i/Simple-Internet-Simulation-using-Packet-Tracer/blob/master/Screenshots/Lenovo%20to%20MSI%20-%20Successful.png)
