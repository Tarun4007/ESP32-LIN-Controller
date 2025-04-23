# ESP32-LIN-Controller-LIN-RGB LED

This project enables communication with LIN LED drivers over the LIN (Local Interconnect Network) protocol using an ESP32 and the MCP2003 LIN transceiver.

### ✅ Features

- LIN Bus wake-up and initialization
- SNPD (auto-addressing) support
- LIN frame sending (including break + sync + PID + checksum)
- Designed to be cost-effective and modular

---

## 🛠️ Hardware

- ESP32 Dev Board
- MCP2003 (LIN Transceiver, 8-PDIP)
- LIN LED Driver 
- 12V DC Power Supply

---

## 🔌 Wiring Overview

| ESP32 Pin | MCP2003 |


---


## 🧠 Communication Flow

### LIN Frame Transmission

Each LIN frame consists of:

1. Break field
2. Sync byte (`0x55`)
3. Protected ID (PID)
4. (Optional) Data bytes
5. Checksum (Classic or Enhanced)

### Reading from a Slave

To request data from a Lumissil slave:

- Send break + sync + PID
- **No data bytes**
- Slave will respond with data if the ID matches

---

## 🧪 Example Code Snippets

### Send LIN Frame (No Data)


sendLINFrame(0x01, {}, false); // Read response from slave at ID 0x01
