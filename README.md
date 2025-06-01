# Remote Heating Control for Summer Cottage (WiFi + TCP/IP)

This project explores a basic wireless solution using the Ublox ODIN-W2 module.  
The goal is to control the heating of a summer cottage from afar — quietly and reliably — using a smartphone and a steady WiFi connection.

## 🌱 Background

In winter, the summer cottage is left cold and empty. When the family plans to return for Christmas, the house must be warm — a process that takes days.  
To avoid waste and discomfort, we wanted to make it possible to turn on the heat in advance from anywhere using just a mobile phone.

No extra devices. No complication. Only what is needed.

## ⚙️ Solution Summary

We used WiFi and TCP/IP protocols to send commands from a smartphone to the cottage's heating system.  
The Ublox ODIN-W2 development board acts as the core communicator, always connected to the cottage WiFi.

The phone becomes the remote — simple and always with the user.

## 🔧 Configuration Steps

Using AT commands, we configured the module like this:

```txt
AT+UBTLE=2             // Enable Bluetooth in peripheral mode
AT&W                   // Save settings
AT+CPWROFF             // Restart device
STARTUP                // Device reboot

AT+UBTLN=Redhaheating   // Bluetooth name
AT+UDSC=1.8.6           // serial port service

AT+UWSCAN               // Scan for available networks
AT+UWSC=0,2,<WiFi Name> // WiFi network name
AT+UWSC=0,8,<Password>  // WiFi password
AT+UWSCA=0,3            // Connect to WiFi

<img width="383" alt="Screenshot 2025-06-01 at 18 41 00" src="https://github.com/user-attachments/assets/e3320520-dd06-4dc0-ac8f-720dcf68c68f" />

