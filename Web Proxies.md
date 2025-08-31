## 🌐 Introduction to Web Proxies

In today’s digital world, nearly every modern web and mobile application constantly communicates with back-end servers. These connections allow applications to send and receive data, which is then processed on the user’s device — whether that’s a web browser or a mobile phone.

Because applications rely so heavily on these back-end systems, **securing and testing them is absolutely essential**. These servers often handle sensitive user data, so any weaknesses can have serious consequences.

As more and more data flows through these channels, the importance of identifying and fixing vulnerabilities in server communications has never been greater.

---

## 🛠️ Why Web Proxies Are Crucial in Security Testing

Analyzing web requests sent to and from a back-end server forms the foundation of **web application penetration testing**. This approach is relevant not just for websites but for mobile apps as well.

Security professionals often need to **capture, analyze, and manipulate these requests** to discover flaws in how data is handled. This process helps uncover misconfigurations, insecure endpoints, or overlooked vulnerabilities — all without needing access to the actual code.

Whether you’re testing a login form or a complex API, understanding the flow of data between client and server is a critical skill — and web proxies make it possible.

## 🔄 What Are Web Proxies?

Web proxies are **specialized tools** that sit between your browser or mobile app and the back-end server. They **intercept and log all the requests and responses** passing between the client and server — essentially acting as **man-in-the-middle tools** designed for testing, not spying.

These tools allow security testers to capture, inspect, and **manipulate web traffic** in real time. For example, when you click a button in a web app, a request is sent to the server and a response is returned. With a web proxy in place, you can capture that request before it reaches the server.

Now imagine — if the request originally grants access to **Section 1049**, a proxy allows you to alter it, perhaps to request **Section 111** or even **Section 1051** — potentially accessing **restricted or premium content** that isn’t normally available to a standard user. This ability to alter and test request behavior is **critical** to identifying flaws in access control and session handling.

---

## 🧭 Web Proxies vs. Network Sniffers

While both web proxies and tools like **Wireshark** capture traffic, their scope and use cases are quite different.

- **Network sniffers** like Wireshark operate at a **lower network layer**. They capture **all traffic** — including web, email, file sharing, and more — across various ports and protocols.
    
- **Web proxies**, on the other hand, are **application-layer tools**. They focus specifically on **HTTP and HTTPS traffic**, which typically operate over **port 80 and port 443**.
    

So while Wireshark gives a **broad view of all network activity**, web proxies give a **detailed, interactive view of web-specific traffic** — and allow for real-time modification.


## 🧰 From CLI Tools to GUI-Based Web Proxies

Before graphical tools became common, capturing and replaying web requests relied heavily on **command-line tools** like `curl`. While powerful, these tools often required manually setting flags, crafting requests, and interpreting raw responses — a process that could be tedious and time-consuming.

With the advancement of web technologies, this workflow was transformed by the introduction of **graphical user interface (GUI) tools**. These tools provided a much more intuitive way to **capture, analyze, and manipulate web traffic**. No more deciphering raw HTTP responses from the terminal — now you could interact with requests visually, in real time.

Web proxies like **Burp Suite** changed the game, allowing for easier request interception and manipulation through a GUI. They became essential tools for modern web application testers, significantly simplifying complex workflows.

---

## 🕵️‍♂️ What Can You Do With a Web Proxy?

Once a web proxy is up and running, you can:

- View **all HTTP(S) requests** made by the application
    
- Inspect **responses** returned from the back-end server
    
- **Intercept and modify** specific requests before they reach the server
    
- See how changes in requests affect application behavior
    

These abilities are foundational in tasks like:

- Web application vulnerability scanning
    
- Web fuzzing (sending varied inputs to test for edge-case failures)
    
- Crawling and mapping an application’s structure
    
- Testing misconfigurations
    
- Performing manual code reviews through traffic analysis
    

Even without exploiting vulnerabilities directly, this level of visibility can reveal serious design flaws.

---

## 🔍 Introducing Burp Suite

One of the most widely used tools for web penetration testing is **Burp Suite** — pronounced just like “burp sweet.”

Burp Suite features a **user-friendly GUI** and includes a **built-in Chromium browser** that can capture traffic seamlessly while you interact with a web app. This browser makes it easy to send specific requests to other Burp tools like **Repeater**, where you can experiment with different inputs and responses.

Even in its **free version**, Burp Suite is powerful. Some advanced capabilities, like:

- **Active scanning** (automated vulnerability scanning)
    
- **Faster Intruder mode** (for automating payload testing)
    
- **Extension support**
    

...are reserved for commercial versions like **Burp Suite Pro** or **Burp Enterprise**.

Still, the free edition offers more than enough firepower for most learning and manual testing needs.

## 🧠 Burp Suite — Beyond the Basics

After getting familiar with Burp Suite's interface and core features, it's time to dig deeper into its **most powerful modules** — the ones that elevate it from a passive interceptor to an active weapon in the hands of a penetration tester.

---

## 🔁 Repeater: Manual Request Manipulation

**Repeater** allows you to take any HTTP request — either intercepted through the proxy or created manually — and resend it as many times as needed, modifying it with each iteration.

This is perfect for:

- Exploring endpoints manually
    
- Testing for vulnerabilities like **authentication bypass**, **SQL injection**, and **parameter tampering**
    
- Observing how subtle changes in input affect responses
    

### Key Features:

- **Graphical editor** for easy modification of headers, parameters, and payloads
    
- Multiple views: raw, hex, rendered response
    
- Full control over each resend attempt
    

### Inspector Panel:

The **Inspector** makes modifying requests easier by breaking them into visual components:

- **Request Attributes**: Change method, path, or protocol (e.g., switch from GET to POST)
    
- **Query Parameters**: Modify `?key=value` pairs in the URL
    
- **Body Parameters**: Useful for POST requests
    
- **Cookies and Headers**: Add, edit, or delete cookies and HTTP headers
    

Inspector is available in both Proxy and Repeater modules, offering a more intuitive alternative to raw text editing.

---

## 🎯 Intruder: Automated Payload Attacks

**Intruder** is Burp's built-in fuzzing engine. It automates the process of sending multiple requests with altered input to test for vulnerabilities.

While the **Community Edition** throttles speed, Intruder still serves as a powerful learning and testing tool.

### Key Use Cases:

- Brute-forcing login credentials
    
- Discovering hidden directories and endpoints
    
- Fuzzing for input validation issues
    

### Intruder Workflow:

1. **Send a request to Intruder** via right-click or `Ctrl + I`
    
2. Define **positions** (injection points) using § markers
    
3. Choose an **attack type**
    
4. Configure **payloads**
    
5. Launch the attack and analyze responses
    

---

### 🧩 Intruder Attack Types

- **Sniper**: Tests one position at a time with all payloads. Great for single-parameter testing (e.g., fuzzing an input field).
    
- **Battering Ram**: Sends the same payload to all positions at once. Useful for duplicate parameter injection.
    
- **Pitchfork**: Assigns one payload set per position and iterates them in parallel. Think of it like testing paired credentials.
    
- **Cluster Bomb**: Tests every possible combination of payloads across positions. Ideal for when you don’t know which credential matches which.
    

---

### ⚙️ Payload Configuration Tabs

- **Positions**: Mark where payloads will be injected
    
- **Payloads**: Load payload sets (manual, list, or file-based)
    
- **Payload Processing**: Add rules to modify, filter, or transform payloads
    
- **Encoding**: Customize how payloads are encoded (e.g., URL encoding)
    

---

## 🔓 Decoder: Data Transformation Toolkit

**Decoder** is your go-to module for encoding, decoding, and hashing data manually. Think of it as a lightweight version of CyberChef built right into Burp.

### Supported Operations:

- **Encoding**: URL, HTML entities, Base64, ASCII Hex, Gzip, etc.
    
- **Decoding**: Smart decode attempts to recursively return encoded data to plaintext
    
- **Hashing**: Generate hashes like MD5 or SHA-1 for data validation
    

Useful for reversing encoded data found in web traffic or preparing encoded payloads for testing.

---

## 🧬 Comparer: Spot the Differences

**Comparer** lets you do a side-by-side comparison of two requests or responses.

### Features:

- Compare by **bytes** or **words**
    
- Sync views between text and hex
    
- Visual highlights for added, removed, or changed content
    

This is helpful for:

- Detecting subtle changes in server behavior
    
- Analyzing how a single payload tweak affects the output
    

---

## 🔢 Sequencer: Analyzing Token Entropy

**Sequencer** is Burp’s tool for analyzing the randomness of tokens like session IDs or CSRF tokens.

### How It Works:

- **Live Capture**: Sends repeated requests and collects token values from responses
    
- **Manual Load**: Import a file of captured tokens for offline analysis
    

Sequencer helps determine if tokens are sufficiently unpredictable — a critical factor in secure session management.


## ⚡️ Getting Started with OWASP ZAP

Just like Burp Suite, **OWASP ZAP** (Zed Attack Proxy) is a web proxy used for intercepting and analyzing HTTP traffic — but it’s completely **open source** and **free**, with many features that rival commercial tools.

---

### 🖥 Launching OWASP ZAP

When ZAP launches, it presents two project options:

- **New Project**: Ideal for persistent testing across multiple sessions
    
- **Temporary Project**: Perfect for short-lived tests or one-time usage
    

For basic tasks and learning purposes, you can typically go with a **temporary project**.

---

### 🌘 Dark Mode and UI Preferences

Many developers and security testers prefer dark themes for comfort during long sessions. Both Burp and ZAP support dark UI themes — ZAP’s interface is fully customizable to fit your visual preferences.

---

## 🌐 Proxy Configuration in Burp Suite & ZAP

Once your tools are up and running, the next critical step is **proxy setup**. The proxy intercept module allows the tool to act as a **man-in-the-middle**, capturing and analyzing all HTTP/S traffic between your browser and the target web application.

---

### 🔌 Understanding the Web Proxy Tab

Both Burp and ZAP allow you to:

- Intercept requests in real time
    
- View and modify traffic manually
    
- Analyze what data is being sent/received
    
- Understand how the application behaves behind the scenes
    

This is fundamental to web application testing, as it reveals hidden requests, headers, cookies, and background communication.

---

## 🧭 Browser Options for Web Proxies

You have **two main options** when using Burp or ZAP as proxies:

### 1. **Use a Preconfigured Browser**

- Burp Suite: Offers a built-in Chromium browser via **"Open Browser"**.
    
- ZAP: Has a shortcut to launch **Firefox** as a preconfigured proxy-enabled browser.
    

These built-in browsers automatically route all traffic through the proxy, making them quick to set up.

> ⚠️ Limitation: Built-in browsers don’t retain your history or bookmarks, and unless you save a project, your activity may be lost. They're useful for quick tasks, but not ideal for long engagements.

---

### 2. **Configure Your Own Browser (Recommended)**

For serious testing, many professionals prefer using **Firefox** or another real browser, which:

- Preserves session history and bookmarks
    
- Offers more flexibility and plugins
    
- Avoids losing progress if the testing session crashes
    

---

### 🔧 Setting Up Firefox Manually

To configure Firefox to work with Burp or ZAP:

1. Go to **Settings → Network Settings → Manual Proxy Configuration**
    
2. Set the HTTP Proxy to `127.0.0.1`
    
3. Set the Port to `8080` (default for both Burp and ZAP)
    
4. Enable “Use this proxy server for all protocols”
    

> ⚠️ If port `8080` is already in use, you'll need to select another available port or shut down the conflicting process.

---

### 🧩 Bonus Tip: Use Proxy Switchers

To make proxy switching easier:

- Use the **FoxyProxy** extension in Firefox
    
- It allows one-click toggling between proxied and direct connections
    

This is especially handy when switching between:

- Browsing normally
    
- Intercepting traffic through Burp or ZAP


## 🔄 Intercepting and Manipulating Requests

One of the most powerful features of any web proxy tool — including Burp Suite and OWASP ZAP — is the ability to **intercept, modify, and forward** web requests. This feature gives penetration testers hands-on control over what’s being sent to the web server.

---

### 🛑 What Happens When You Intercept

Once you’ve enabled interception in Burp or ZAP:

- Every HTTP request is paused before it reaches the server.
    
- You can:
    
    - **Inspect** the request in detail
        
    - **Modify** headers, parameters, cookies, and even methods (GET → POST, etc.)
        
    - **Forward** the request as-is or after changes
        
    - **Drop** the request entirely
        
    - **Send** it to other tools like Repeater for testing
        

> ⚠️ Be aware: It can be annoying when every request pauses your browsing. Use **intercept tactically** — turn it **on** only when needed.

---

## ✍️ Why Modify Requests?

Manipulating requests reveals how web apps handle:

- Unexpected inputs
    
- Invalid formats
    
- Changed cookies or headers
    
- Tampered parameters
    

This is often the **first step** in discovering vulnerabilities. You’re effectively **testing trust boundaries** in how the server handles data from the client.

---

## 💣 Real-World Testing Use Cases

Manipulating requests is useful in a variety of real-world attacks:

- 🔹 **SQL Injection**
    
- 🔹 **Command Injection**
    
- 🔹 **Upload Bypasses**
    
- 🔹 **Authentication Bypass**
    
- 🔹 **Cross-site Scripting (XSS)**
    
- 🔹 **XML External Entity (XXE) Attacks**
    
- 🔹 **Improper Error Handling**
    
- 🔹 **Insecure Deserialization**
    

> Don’t worry if you’re unfamiliar with these terms. We’ll break them down one by one in future missions.

---

## 🧪 Practical Example: Manipulating Input

Let’s say we’re interacting with a form that allows users to **ping an IP address**.

- Normally, the front-end only accepts numbers — validated by JavaScript.
    
- But through intercepting the request, we can change the IP input from a number like `127.0.0.1` to something else — say, `; cat /etc/passwd`.
    

If the back-end fails to properly validate input, this could result in **command injection**.

You might even find sensitive files like `flag.txt` returned in the response.

---

## 🧃 Beyond Requests: Intercepting Responses

Sometimes, the **server response** is just as important.

Intercepting responses lets you:

- Analyze **headers** returned by the server
    
- Detect possible **leaks** or error messages
    
- Spot **injected scripts** or altered content
    
- Experiment with **modifying** returned data before it reaches the browser (e.g., changing roles from "user" to "admin")
    

This level of control gives pentesters the edge in both **discovering** and **exploiting** vulnerabilities.