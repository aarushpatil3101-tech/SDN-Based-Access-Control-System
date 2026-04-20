# SDN-Based Access Control System

## 📌 Overview
This project implements an SDN-based access control system using the Ryu controller and Mininet. It allows only authorized hosts (based on MAC address) to communicate within the network.

---

## 🎯 Objectives
- Maintain a whitelist of hosts
- Allow communication only for authorized hosts
- Block unauthorized access
- Dynamically install flow rules
- Verify access control and ensure policy consistency

---

## 🛠️ Tools & Technologies
- Python
- Ryu SDN Controller
- Mininet
- OpenFlow (v1.3)

---

## 📂 Project Structure
- controller.py → Ryu controller logic
- topology.py → Mininet network setup
- README.md → Documentation

---

## ⚙️ Setup Instructions

### 1. Install Dependencies
```bash
sudo apt update
sudo apt install mininet
pip install ryu
```

### 2. Run the Controller
```bash
ryu-manager controller.py
```

### 3. Run the Network
```bash
sudo python3 topology.py
```

---

## 🔐 Access Control Logic
- The controller checks the source MAC address of incoming packets.
- If the MAC is in the whitelist → traffic is allowed.
- Otherwise → traffic is blocked.

---

## 🧪 Testing

Inside Mininet CLI:
```bash
h1 ping h2   # Allowed
h3 ping h2   # Blocked
```

---

## 🔍 Expected Output
- Allowed hosts communicate successfully
- Unauthorized hosts cannot communicate
- Controller logs show "Allowed" or "Blocked" decisions

---

## 🔄 Regression Testing
- Add/remove hosts from whitelist and verify behavior
- Restart controller and confirm policies persist
- Ensure existing rules are not broken by updates

---

## 📌 Future Enhancements
- IP-based filtering
- Web-based dashboard
- Role-based access control
- Integration with real networks

---

## 📝 Summary
This project demonstrates how SDN enables centralized and dynamic network security by enforcing access control policies efficiently.
