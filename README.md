
# Who’s Online? – LAN Scanner using UDP Broadcast in Java

A lightweight Java-based tool to discover online devices in your Local Area Network (LAN) using UDP broadcast. It sends a ping to all devices and listens for replies from those running a responder. Includes a simple graphical interface for ease of use.

---

## Features

- Broadcasts a UDP "Are you online?" message to all LAN devices.
- Devices running the responder reply with hostname and IP.
- Displays responses in a GUI console.
- Works across laptops, PCs, or even mobile devices via Termux.
- Fast and lightweight – no external dependencies.

---

## Project Structure

```

.
├── UDPPingBroadcaster.java     # GUI + UDP broadcaster
├── UDPResponder.java           # Device-side responder
├── Main.java                   # Optional launcher class
└── README.md

````

---

## Setup & Running

### Requirements
- Java 11+ (Tested on OpenJDK 21)
- Any Java IDE (IntelliJ, Eclipse, VSCode) or terminal

### Run the Responder (on one or more devices)
```bash
javac UDPResponder.java
java UDPResponder
````

This listens on port 8888 and replies when a broadcast is received.

### Run the GUI Broadcaster (on your main device)

```bash
javac UDPPingBroadcaster.java
java UDPPingBroadcaster
```

Click "Scan" – it will send the broadcast and display any replies received.

---

## Running on Android (Optional)

You can run the responder on Android using Termux:

1. Install Termux from F-Droid.
2. Run:

   ```bash
   pkg update
   pkg install openjdk
   javac UDPResponder.java
   java UDPResponder
   ```
3. Ensure phone is on the same Wi-Fi as your PC.

---

## Concepts Covered

* Java UDP Sockets (`DatagramPacket`, `DatagramSocket`)
* Broadcasting in LAN (`255.255.255.255`)
* Swing GUI (Buttons, Threads, Console)
* Threaded listener for real-time responses

---

## Future Enhancements(Currently working on)

* Export scan results to file
* Scheduled periodic scans
* Identify device types or OS
* Integrate with a database for logging

---

## License

This project is open-source and free to use under the MIT License.

---

## Author

Karthik Reddy
Feel free to connect or star this repo if you found it helpful.

```


