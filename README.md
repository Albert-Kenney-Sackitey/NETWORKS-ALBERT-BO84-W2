# NETWORKS-ALBERT-BO84-W2
PENETRATION TESTING REPORT

FOOTPRINTING & NETWORK SCANNING PHASES

W2-PM-FINAL | CYBERSECURITY | NETWORKWALKS

Pentester Name (Cybersecurity Professional)

Albert Kenney Sackitey

Program/Batch

B084-Networkwalks

Date

9th Nov 2026

Modules Completed

W2-PM4 (Footprinting & Reconnaissance with theHarvester)

W2-PM5 (Network Scanning with Zenmap)

Client / Target Scope

networkwalks.com / microsoft.com (secured written permission already)

Local LAN Network

Permission Secured from Client?

Yes

Phases Covered

Phase 1: Reconnaissance & Footprinting

Phase 2: Scanning & Network Discovery

Phase 3–5: In Progress

1. Liability Disclaimer

I have performed these activities only on the systems & devices where I had secured written permission or the devices/systems that I own myself. All these materials are for education and research purpose only. Do not use anything from here to break the law. The instructor, the authors, and Networkwalks are not responsible for what you do with this knowledge. Every action you take is your own responsibility. Misuse can lead to criminal charges, heavy fines, loss of your job, and a permanent record. In most countries, unauthorized access is a crime even when nothing is damaged.

2. Introduction

This report covers passive footprinting and reconnaissance against target domains using theHarvester (W2-PM4) and active network discovery on a local subnet using Zenmap (W2-PM5). Together, these modules demonstrate how a security professional moves from open-source intelligence (OSINT) gathering to mapping live hosts on a network. This forms part of the Week 2 practical requirements of the ongoing internship program at Networkwalks.

All commands were executed within a Kali Linux environment (for footprinting) and on a Windows PC running Zenmap (for scanning). Every step below includes the tool used, the exact command, observed results, and the security impact from an attacker's perspective.

3. Tools Used

Tool

Purpose

Kali Linux & Windows

Operating systems utilized for reconnaissance, footprinting, and host discovery activities.

theHarvester

Gather open-source intelligence (OSINT) such as emails, subdomains, and hosts from public search engines without directly touching target servers.

Zenmap (Nmap GUI)

Scan local subnets to discover live hosts, IP addresses, MAC addresses, and generate network topology layouts.

Windows CMD (ipconfig)

Identify local IP configuration, adapter details, and LAN subnet architecture.

4. Activities Performed

4.1 Footprinting & Reconnaissance with theHarvester

Passive OSINT collection was conducted using theHarvester version 4.10.1 in Kali Linux against target domains to extract publicly available data without alerting the target organization:

Single-Source Search (Baidu):

Command: theHarvester -d microsoft.com -l 1000 -b baidu

Observation: Scanned up to 1,000 results via Baidu, successfully identifying public organizational artifacts including email accounts (e.g., viva-noreply@microsoft.com).

Multi-Source Search (All Sources):

Command: theHarvester -d microsoft.com -l 50 -b all

Observation: Queried multiple public engines and records (handling missing API keys gracefully) to compile broader infrastructure handles, emails, and host mappings.

4.2 Network Scanning with Zenmap

Network discovery and host mapping were performed on the local LAN environment:

Subnet Discovery: Executed ipconfig via Windows Command Prompt to determine the local host IP address and LAN subnet range.

Ping Scan Execution: Inputted the local subnet into Zenmap with the Ping Scan profile (nmap -sn 10.0.0.0/24).

Discovered Live Hosts & MAC Addresses:

10.0.0.2 — MAC: 00:50:56:E3:B3:3b (up)


Topology Mapping: Enabled the Topology view, inspected the legend, and exported the visual network topology map in PDF format to the desktop.

5. Risk Analysis / Impact

#

Risk / Finding

Evidence / Observation

Potential Impact

Risk Level

1

Passive Email Address Exposure

theHarvester successfully extracted public corporate email addresses.

Harvested emails can be leveraged by attackers to execute targeted spear-phishing campaigns and brute-force attacks.

● Medium

2

Subdomain & Infrastructure Leakage

OSINT tools extracted public subdomains and host mappings.

Exposes forgotten or unmonitored entry points into an organization's network perimeter.

● Medium

3

Internal Subnet Host Visibility

Zenmap ping scan revealed active local hosts, IP addresses, and NIC vendor fingerprints.

Allows local attackers or compromised machines to map adjacent devices and plan lateral movement.

● Medium

Risk Level Key: ● Critical | ● Medium | ● Low

6. Recommendations

Reduce Public Digital Footprint: Minimize the publication of employee email addresses and internal domain structures on public directories and search engines.

Perform Regular OSINT Audits: Routinely run tools like theHarvester internally to view your organization through an attacker's lens and clean up leaked data.

Network Segmentation & Monitoring: Implement strict network segmentation to restrict unauthorized internal host discovery and monitor subnet ping sweeps.

Device Inventory Management: Maintain accurate asset documentation for all active devices and virtual machines discovered on local subnets.

Strict Authorization Scope: Ensure all scanning and reconnaissance activities are strictly restricted to authorized lab environments or targets with explicit written consent.

7. Conclusion

During Week 2 of the Cybersecurity & Ethical Hacking internship at Networkwalks, practical execution of passive footprinting using theHarvester and active network scanning using Zenmap was successfully completed.

The exercises demonstrated that significant intelligence can be gathered passively via OSINT engines without ever directly interacting with a target system, minimizing detection risks. Furthermore, active subnet scanning with Zenmap provided clear visualization of live hosts, MAC vendors, and network topologies. These competencies underscore the critical need for organizations to minimize public data exposure and maintain tight internal network visibility.

8. Evidences Collected

Terminal execution logs for theHarvester, Zenmap scan outputs, host topology diagrams, and PDF exports are securely saved within the project repository archive.
