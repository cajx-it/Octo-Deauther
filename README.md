# Octo

<p align="center">
  <img src="resources/logo.png" width="250" alt="Octo Logo">
</p>

<p align="center">
  <strong>Server Type ESP8266 2.4 GHz Wi-Fi Deauther</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/ESP8266-Platform-blue" alt="ESP8266">
</p>

---

## About

**Octo** is an ESP8266 Deauther Server Type built around a client/server
architecture.

The ESP8266 runs the Octo firmware and communicates with a centralized Octo
Server through WebSocket. The system provides wireless network information,
device monitoring, remote communication, and controlled deauthentication-frame
testing for authorized environments.

The project was developed to explore:

- ESP8266 wireless capabilities
- Wi-Fi network discovery
- Wireless signal analysis
- Embedded networking
- WebSocket communication
- Remote ESP8266 device management
- Authorized wireless security testing

> **Important:** Octo's wireless testing functionality is intended only for
> networks and devices that you own or have explicit authorization to test.

---

# Features

## ESP8266

- Wi-Fi network scanning
- SSID discovery
- BSSID discovery
- RSSI / signal-strength monitoring
- Wi-Fi configuration
- WebSocket client
- Automatic server communication
- Persistent configuration
- Controlled deauthentication-frame testing for authorized environments

## Octo Server

- WebSocket server
- ESP8266 device management
- Device connection monitoring
- Online/offline status
- Remote device communication
- Real-time device updates
- Multiple ESP8266 client support
- Centralized wireless-testing control

---

# Architecture

Octo uses a client/server architecture.

```text
                         ┌──────────────────────────┐
                         │       OCTO SERVER        │
                         │                          │
                         │      WebSocket :8888     │
                         └────────────┬─────────────┘
                                      │
                       WebSocket      │
                                      │
              ┌───────────────────────┼───────────────────────┐
              │                       │                       │
              ▼                       ▼                       ▼
       ┌────────────┐          ┌────────────┐          ┌────────────┐
       │  ESP8266   │          │  ESP8266   │          │  ESP8266   │
       │   Octo #1  │          │   Octo #2  │          │   Octo #3  │
       └────────────┘          └────────────┘          └────────────┘
              │                       │                       │
              ▼                       ▼                       ▼
        Wi-Fi Testing           Wi-Fi Testing           Wi-Fi Testing
