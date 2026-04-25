# WIDS-ESP32
An ESP32-based Wireless Intrusion Detection System (WIDS) that identifies common WiFi attacks in real-time. The system hosts a web dashboard accessible at http://192.168.4.1 after connecting to the ESP32-IDS access point, providing live attack alerts and traffic visualization.


The ESP32 creates its own WiFi access point named `ESP32-IDS`. To access the dashboard:

1. Scan for available WiFi networks from your computer or mobile device
2. Connect to the network named `ESP32-IDS`
3. Enter the password: `12345678`
4. Open a web browser and navigate to `http://192.168.4.1`
5. The dashboard displays real-time threat scores, packet statistics, and attack alerts

No internet connection is required to access the dashboard as the ESP32 operates as a standalone access point.
