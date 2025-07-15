- The **OSI** model (or **O**pen **S**ystems **I**nterconnection Model) is an essential model used in networking
- This critical model provides a framework dictating how all networked devices will send, receive and interpret data.
- The OSI model consists of seven layers which are illustrated in the diagram below. Each layer has a different set of responsibilities and is arranged from Layer 7 to Layer 1.
- At every individual layer that data travels through, specific processes take place, and pieces of information are added to this data

![OSI Model](images/Pasted image 20250714005710.png)

***Have you ever wondered what happens behind the scenes when you fire a shot in Call of Duty and it lands on a player halfway across the world? How does your action become data and travel through the internet so fast? But what actually happens behind the scenes from your tap... to the bullet hitting the enemy? It's done using the OSI Model.***

---

## **Seven Layers Of OSI Model**

### ***Layer 7:- Application Layer***

> *The application layer of the OSI model is the layer that you will be most familiar with. This familiarity is because the application layer is the layer in which protocols and rules are in place to determine how the user should interact with data sent or received.*

![App Layer](images/Pasted image 20250617183139.png)

🎮 _“You tap the fire button.”_

This is the layer where _you_, the user, directly interact.  
You press shoot → the game prepares to send data: _“PlayerX fired bullet at coordinate (X,Y)._

---

### **Layer 6 – Presentation Layer**

> *This layer acts as a translator for data to and from the application layer (layer 7). The receiving computer will also understand data sent to a computer in one format destined for in another format*  
> *Data is compressed and encrypted in this layer.*

CODM doesn't want raw data flying over the internet — so your shooting data is compressed and possibly encrypted to save bandwidth and keep it secure.  
COD also compresses your mic audio or encrypts voice chat before sending.  
This layer _formats, compresses, and encrypts_ your data.

---

### **Session Layer-(Layer 5)**

> *Once data has been correctly translated or formatted from the presentation layer (layer 6), the session layer (layer 5) will begin to create and maintain the connection to other computers for which the data is destined...*

You’re in an active session with COD servers. This layer ensures your connection is still open, and if you lag or disconnect, it knows how to reinitiate or recover the session.

---

### **Transport Layer (Layer 4)**

> When data is sent between devices, it follows one of two different protocols:
- TCP
- UDP

#### TCP (Transmission Control Protocol)
> *This protocol is designed with reliability and guarantee in mind. It reserves a constant connection, checks for errors, ensures chunks are received in the right order...*

Used for:
- File sharing
- Web browsing
- Email

#### UDP (User Datagram Protocol)
> *This is simpler, faster, no guarantee of delivery.*

Used for:
- Gaming (like your shooting action)
- Video streaming

Your ‘fire’ action is broken into smaller chunks and sent. COD uses **UDP** because it’s faster — even if some packets drop, the game continues.

---

### **Layer 3 – Network Layer**

> *This is where the magic of routing & re-assembly of data takes place...*

Your data gets an **IP address** — like writing a destination on a letter. It figures out how to reach the game server (e.g., `203.0.113.50`).

---

### **Layer 2 – Data Link Layer**

> *This focuses on the physical addressing of the transmission.*

Your device adds the **MAC address** — like tagging which device the data is coming from. This is how your local router knows which phone sent the shot.

---

### **Layer 1 – Physical Layer**

> *This references the physical components of the hardware. Devices use electrical signals to transfer data...*

Now the final bullet data is turned into _electrical signals_, _Wi-Fi waves_, or _fiber-optic pulses_ that travel through your device → router → ISP → COD server.

---

## 🎯 **The Bullet Hits! (Server to Enemy)**

Once it reaches the server, the server processes your shot, checks hit detection, and sends the result back — _“Enemy took 20 damage.”_

That return trip also goes back **up** the OSI model, from physical all the way up to application — where the health bar of your enemy drops on their screen.

---

### **Final Recap (Bullet Summary)**

📌Summary

| Layer Number | Layer Name        | Main Function                                 | Example Protocols                        |
|--------------|-------------------|-----------------------------------------------|------------------------------------------|
| Layer 7      | Application        | Providing services and interfaces to apps     | HTTP, FTP, DNS, POP3, SMTP, IMAP         |
| Layer 6      | Presentation       | Data encoding, encryption, and compression     | Unicode, MIME, JPEG, PNG, MPEG           |
| Layer 5      | Session            | Session management                             | NFS, RPC                                 |
| Layer 4      | Transport          | Communication, segmentation                    | TCP, UDP                                 |
| Layer 3      | Network            | Logical addressing, routing                    | IP, ICMP, IPSec                          |
| Layer 2      | Data Link          | Local delivery, MAC addressing                 | Ethernet, WiFi                          |
| Layer 1      | Physical           | Raw signal transmission                        | Electrical, Optical, Wireless            |

**Layer Summary:**
- Application: You tap shoot  
- Presentation: Data is formatted/encrypted  
- Session: Connection is managed  
- Transport: Data chunked via UDP  
- Network: Routed using IP  
- Data Link: MAC attached  
- Physical: Wi-Fi sends it off  

---

**📢 Disclaimer:**  
This video is created solely for educational purposes and is the intellectual property of its creator. It is not affiliated with or owned by any platform, including Call of Duty, or any third party mentioned for context.  
**Do not misuse or reupload this content without permission.**

🎭 Property of: Alpha Bey
