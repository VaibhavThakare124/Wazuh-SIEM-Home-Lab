# Wazuh SIEM Home Lab

## 📌 Project Overview

This project is a hands-on **Wazuh SIEM home lab** built to practice security monitoring, endpoint visibility, File Integrity Monitoring (FIM), alert generation, and basic SIEM operations.

The lab uses a virtualized environment with **Ubuntu, Wazuh, Windows, and Tailscale**.

The main objective was to understand how a SIEM can monitor endpoint activity and generate security events in real time.

---

## 🏗️ Lab Architecture

```text
                Windows Host
                    │
                    │
              Tailscale Network
                    │
                    ▼
              Ubuntu VM
                    │
                    ▼
               Wazuh SIEM
                    │
                    ▼
            Wazuh Dashboard
                    │
                    ▼
        File Integrity Monitoring
                    │
                    ▼
              Test Directory
```

---

## 🛠️ Technologies Used

* Wazuh SIEM
* Ubuntu
* Windows
* VirtualBox
* Tailscale
* File Integrity Monitoring (FIM)
* XML configuration
* Windows endpoint monitoring

---

## 🔧 Lab Implementation

### 1. Wazuh Deployment

Wazuh was deployed in an Ubuntu virtual machine.

The environment included the Wazuh manager and dashboard for security event monitoring.

---

### 2. Windows Endpoint Monitoring

A Windows endpoint was connected to the Wazuh environment and used as the monitored endpoint.

The objective was to generate controlled file activity and verify that the events were detected by Wazuh.

---

### 3. File Integrity Monitoring

A test directory was configured for real-time monitoring.

Example configuration:

```xml
<directories realtime="yes">C:\test-files</directories>
```

This configuration enables Wazuh to monitor changes within the specified directory.

---

### 4. Testing Real-Time Detection

Controlled file activities were performed inside the monitored directory.

For example:

* Creating files
* Modifying files
* Deleting files

The resulting activity was then observed through the Wazuh dashboard.

---

## 🔎 Detection Validation

The lab successfully detected file activity from the monitored Windows directory.

The generated events were visible through the Wazuh dashboard, demonstrating the complete monitoring flow:

```text
File Activity
      ↓
Windows Endpoint
      ↓
Wazuh Agent
      ↓
Wazuh Manager
      ↓
Wazuh Dashboard
      ↓
Security Event
```

---

## 🌐 Network Stability with Tailscale

One practical challenge was maintaining stable connectivity between the lab components.

Changing networks could cause IP addresses to change, making communication between systems inconvenient.

To address this, **Tailscale** was used to provide stable connectivity between the systems.

This reduced the need to repeatedly update IP-based configurations when changing networks.

---

## ⚙️ Troubleshooting

The lab was built on a system with limited RAM, which caused performance issues when running the Wazuh environment directly inside the Ubuntu VM.

Instead of abandoning the lab, the deployment was adapted to reduce the resource load.

Network configuration was also adjusted using a bridged adapter so that the required communication between the Windows host and Ubuntu environment could be established.

This provided practical experience with:

* Virtual machine resource limitations
* Linux/Windows networking
* Bridged networking
* Endpoint-to-SIEM connectivity
* Troubleshooting SIEM deployments

---

## 📸 Screenshots

### Wazuh Dashboard

*Add dashboard screenshot here.*

### File Integrity Monitoring Alert

*Add FIM alert screenshot here.*

### File Activity

*Add screenshot showing the test file activity.*

### Agent Status

*Add Wazuh agent status screenshot here.*

---

## 🎯 Key Learning Outcomes

Through this project I gained practical experience with:

* SIEM deployment
* Endpoint monitoring
* File Integrity Monitoring
* Real-time security event detection
* Wazuh dashboard investigation
* Windows endpoint monitoring
* Linux administration
* Virtual machine networking
* Tailscale networking
* Troubleshooting resource and connectivity issues

---

## 🚀 Future Improvements

Possible future improvements include:

* Integrating additional log sources
* Creating custom detection rules
* Adding vulnerability detection
* Integrating WAF security events
* Building additional attack-and-detection scenarios
* Expanding the lab into a larger SOC simulation

---

## ⚠️ Disclaimer

This project was created in a controlled home-lab environment for educational and cybersecurity learning purposes.

All testing was performed against systems under my control.

