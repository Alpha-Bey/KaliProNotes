- The **OSI** model (or **O**pen **S**ystems **I**nterconnection Model) is an essential model used in
- 
- networking
- This critical model provides a framework dictating how all networked devices will send, receive and interpret data.
- The OSI model consists of seven layers which are illustrated in the diagram below. Each layer has a different set of responsibilities and is arranged from Layer 7 to Layer 1.
- At every individual layer that data travels through, specific processes take place, and pieces of information are added to this data
-
                        ![[Pasted image 20250713053406.png]]
                        
*Have you ever wondered what happens behind the scenes when you fire a shot in Call of Duty and it lands on a player halfway across the world? How does your action become data and travel through the internet so fast?But what actually happens behind the scenes from your tap... to the bullet hitting the enemy? Its done using the OSI Model.*



**Seven Layers Of OSI Model**

***Layer 7:- Application Layer***

>*The application layer of the OSI model is the layer that you will be most familiar with. This familiarity is because the application layer is the layer in which protocols and rules are in place to determine how the user should interact with data sent or received*


>>>
>>>>>>>>>>>![[Pasted image 20250617183139.png]]
🎮 _“You tap the fire button.”_

This is the layer where _you_, the user, directly interact.  
You press shoot → the game prepares to send data: _“PlayerX fired bullet at coordinate (X,Y)._

**Layer 6 – Presentation Layer**
>*- This layer acts as a translator for data to and from the application layer (layer 7). The receiving computer will also understand data sent to a computer in one format destined for in another format*
>*- Data is compressed and encrypted. in this layer.*

 CODM doesn't want raw data flying over the internet — so your shooting data is compressed and possibly encrypted to save bandwidth and keep it secure.
 COD also compresses your mic audio or encrypts voice chat before sending. This layer _formats, compresses, and encrypts_ your data

**Session Layer-(Layer 5)**
>*Once data has been correctly translated or formatted from the presentation layer (layer 6), the session layer (layer 5) will begin to create and maintain the connection to other computer for which the data is destined. When a connection is established, a session is created. Whilst this connection is active, so is the session.*

You’re in an active session with COD servers. This layer ensures your connection is still open, and if you lag or disconnect, it knows how to reinitiate or recover the session.

**Transport Layer (Layer 4)**
>When data is sent between devices, it follows one of two different protocols that are decided based upon several factors:

- TCP
- UDP
>>>>>>>*The **T**ransmission **C**ontrol **P**rotocol (**TCP**). Potentially hinted by the name, this protocol is designed with reliability and guarantee in mind. This protocol reserves a constant connection between the two devices for the amount of time it takes for the data to be sent and received.*
>>*Not only this, but TCP incorporates error checking into its design.* 
 *Error checking is how TCP can guarantee that data sent from the small chunks in the session layer (layer 5) has then been received and reassembled in the same order.*
>*TCP is used for situations such as file sharing, internet browsing or sending an email. This usage is because these services require the data to be accurate and complete (no good having half a file!).*

>>>>>>>>***User Datagram Protocol (or U*DP for short**). This protocol is not nearly as advanced as its brother - the TCP protocol. It doesn't boast the many features offered by TCP, such as error checking and reliability. In fact, any data that gets sent via UDP is sent to the computer whether it gets there or not. There is no synchronisation between the two devices or guarantee; just hope for the best, and fingers crossed.*

>>*UDP is useful in situations where there are small pieces of data being sent. For example, protocols used for discovering devices (ARP and DHCP that we discussed in or larger files such as video streaming (where it is okay if some part of the video is pixelated. Pixels are just lost pieces of data!)*

Your ‘fire’ action is broken into smaller chunks and sent. For real-time gameplay, COD uses **UDP** because it’s faster — even if some packets drop, the game continues.
- UDP: For game movement/shooting – speed matters
    
- TCP: For chat or login – reliability matters


**Layer 3 – Network Layer**
>*The third layer of the OSI model (network layer) is where the magic of routing & re-assembly of data takes place (from these small chunks to the larger chunk). Firstly, routing simply determines the most optimal path in which these chunks of data should be sent.*
>- What path is the shortest? I.e. has the least amount of devices that the packet needs to travel across.
>- What path is the most reliable? I.e. have packets been lost on that path before?
>- Which path has the faster physical connection? I.e. is one path using a copper connection (slower) or a fibre (considerably faster)?

Example:- when u shoot in COD
_Where is this shot going?

Your data gets an **IP address** — like writing a destination on a letter. It figures out how to reach the game server (e.g., `203.0.113.50`) across the internet.

**Layer 2 – Data Link Layer**
>*The data link layer focuses on the physical addressing of the transmission. It receives a packet from the network layer (including the IP address for the remote computer) and adds in the physical **MAC** (Media Access Control) address of the receiving endpoint. Inside every network-enabled computer is a **N**etwork **I**nterface Card (**NIC**) which comes with a unique MAC address to identify it.         

“Attach MAC address & send over LAN/WiFi.”_
Your device adds the **MAC address** — like tagging which device the data is coming from. This is how your local router knows which phone sent the shot.

**Layer 1 – Physical Layer**
>*This layer is one of the easiest layers to grasp. Put simply, this layer references the physical components of the hardware used in networking and is the lowest layer that you will find. Devices use electrical signals to transfer data between each other in a binary numbering system (1's and 0's).*


Now the final bullet data is turned into _electrical signals_, _Wi-Fi waves_, or _fiber-optic pulses_ that travel through your device → router → ISP → COD server.
your mouse or keyboard or controller from which you are playing call off duty (COD)

## 🎯 **The Bullet Hits! (Server to Enemy)**

Once it reaches the server, the server processes your shot, checks hit detection, and sends the result back — _“Enemy took 20 damage.”_

That return trip also goes back **up** the OSI model, from physical all the way up to application — where the health bar of your enemy drops on their screen.
### **Final Recap (Bullet Summary)**

📌Summary


***Layer Number |Layer Name |Main Function |Example Protocols*** 
>L*ayer 7   Application layer Providing services and interfaces to applications 	HTTP, FTP, DNS, POP3, SMTP, IMAP*
>*Layer 6 	Presentation layer 	Data encoding, encryption, and compression 	Unicode, MIME, JPEG, PNG, MPEG*
>*Layer 5 	Session layer 	Establishing, maintaining, and synchronising sessions 	NFS, RPC*
>*Layer 4 	Transport layer 	End-to-end communication and data segmentation 	UDP, TCP*
>*Layer 3 	Network layer 	Logical addressing and routing between networks 	IP, ICMP, IPSec*
>*Layer 2 	Data link layer 	Reliable data transfer between adjacent nodes 	Ethernet (802.3), WiFi (802.11)*
>*Layer 1 	Physical layer 	Physical data transmission media 	Electrical, optical, and wireless signals*

- **Application:** You tap shoot
    
- **Presentation:** Data is formatted/encrypted
    
- **Session:** Connection is managed
    
- **Transport:** Data chunked via UDP
    
- **Network:** Routed using IP
    
- **Data Link:** MAC attached
    
- **Physical:** Wi-Fi sends it off



**📢 Disclaimer:**  
This video is created solely for educational purposes and is the intellectual property of its creator. It is not affiliated with or owned by any platform, including  Call of Duty, or any third party mentioned for context.  
**Do not misuse or reupload this content without permission.**

🎭 Property of: Alpha Bey





