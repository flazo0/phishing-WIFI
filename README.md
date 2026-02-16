# ESP32 Wireless Security Research

### Infrastructure-Level Wi-Fi Threat Modeling Study

## Overview

This repository documents a controlled security research project analyzing infrastructure-level phishing risks in unsecured Wi-Fi environments using low-cost embedded hardware (ESP32).

The objective of this research was to understand how rogue access point scenarios operate conceptually, how users are influenced by trusted SSIDs, and how DNS manipulation combined with captive portal behavior can be leveraged in phishing-style attacks.

This project was conducted strictly in an isolated lab environment for educational and defensive research purposes.

---

## Threat Model

This research focuses on a common wireless attack pattern often referred to as a **rogue access point scenario**.

In this model:

1. An attacker deploys a wireless access point broadcasting a familiar or generic SSID.
2. Users connect under the assumption that the network is legitimate.
3. Network traffic is manipulated at the infrastructure level.
4. Victims are redirected to controlled web interfaces.
5. Social engineering techniques are used to elicit sensitive input.

The attack relies primarily on:

* User trust in open Wi-Fi networks
* Lack of certificate validation awareness
* DNS-level traffic manipulation
* Behavioral assumptions about captive portals

No real credentials were collected during this research.

---

## Architectural Components (Conceptual)

The simulated environment analyzed the following technical layers:

### 1. Wireless Layer

* SoftAP behavior in embedded hardware
* DHCP-based client provisioning
* Local network isolation

### 2. DNS Interception Layer

* Catch-all DNS response behavior
* Forced redirection patterns
* Impact on client browsing flows

### 3. HTTP Layer

* Captive portal-like redirection logic
* Web interface rendering
* Input handling simulation (non-persistent)

### 4. Behavioral Layer

* Visual trust replication
* Cognitive bias exploitation
* Error-page reinforcement patterns

---

## How the Attack Works (Conceptual Flow)

1. A rogue wireless network becomes available.
2. A user connects to the network.
3. DNS resolution is manipulated to point all domains to a local server.
4. The user is redirected to a web interface resembling a login portal.
5. Social engineering techniques encourage credential submission.
6. The user perceives an error and may retry, reinforcing trust.

This mechanism exploits infrastructure positioning rather than software vulnerabilities.

---

## Risk Analysis

The study highlights several security risks:

* High success probability in public Wi-Fi environments
* Low hardware cost barrier
* Minimal technical footprint
* Difficulty of detection by non-technical users
* Reliance on human factors rather than zero-day exploits

It demonstrates how infrastructure manipulation can bypass user caution if layered defenses are absent.

---

## Defensive Considerations

This research reinforces the importance of:

* HTTPS enforcement with strict HSTS policies
* Certificate validation awareness
* Multi-Factor Authentication (MFA)
* VPN usage on public networks
* Rogue Access Point detection systems
* Network monitoring for abnormal DNS behavior
* User security awareness training

---

## Hardware Limitations Observed

The ESP32 platform, while capable of simulating wireless behaviors, presents constraints:

* Limited memory for request handling
* Restricted concurrent connection capacity
* Basic HTTP serving capabilities
* No TLS termination without external complexity

These limitations impact realism and scalability in practical scenarios.

---

## Ethical & Legal Notice

All experimentation was conducted:

* In a fully isolated laboratory environment
* Without public network exposure
* Without real credential collection
* Without third-party interaction

This repository does not contain deployable attack tools or operational phishing kits.

The purpose of this research is to improve understanding of wireless infrastructure risks and strengthen defensive security practices.

Unauthorized deployment of similar techniques in real-world environments is illegal and unethical.

---

## Conclusion

This project serves as a structured exploration of wireless threat modeling, infrastructure-based phishing mechanisms, and the interaction between embedded systems and human trust.

It bridges theoretical cybersecurity knowledge with controlled experimental validation to improve defensive awareness in modern Wi-Fi environments.
