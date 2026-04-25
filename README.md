# WIDS-ESP32
An ESP32-based Wireless Intrusion Detection System (WIDS) that identifies common WiFi attacks in real-time. The system hosts a web dashboard accessible at http://192.168.4.1 after connecting to the ESP32-IDS access point, providing live attack alerts and traffic visualization.


The ESP32 creates its own WiFi access point named `ESP32-IDS`. To access the dashboard:

1. Scan for available WiFi networks from your computer or mobile device
2. Connect to the network named `ESP32-IDS`
3. Enter the password: `12345678`
4. Open a web browser and navigate to `http://192.168.4.1`
5. The dashboard displays real-time threat scores, packet statistics, and attack alerts

No internet connection is required to access the dashboard as the ESP32 operates as a standalone access point.

##  How It Works

### 802.11 Frame Capture

The ESP32 operates in **promiscuous mode**, which allows it to capture all 802.11 wireless frames within range, not just those addressed to it. This includes:

| Frame Type | Description |
|------------|-------------|
| **Management Frames** | Control network operations (probes, beacons, authentication, deauthentication) |
| **Control Frames** | Manage channel access and acknowledgments |
| **Data Frames** | Carry actual network payloads |

### Frame Types Detected by This System

| Management Frame | Normal Purpose | Attack Indicator |
|-----------------|----------------|------------------|
| Probe Request | Device searching for networks | Sudden spike > threshold indicates probe flood |
| Beacon | Router announcing its presence | Excessive beacons (>350/sec) indicates beacon flood |
| Deauthentication | Forceful disconnection of a device | High frequency indicates deauth attack |
| Authentication | Device proving identity to join network | Rapid succession indicates auth attack |

DISCLAIMER
This tool has been made for educational and testing purposes only. Any misuse or illegal activities conducted with the tool are strictly prohibited. I am not responsible for any consequences arising from the use of the tool, which is done at your own risk.
