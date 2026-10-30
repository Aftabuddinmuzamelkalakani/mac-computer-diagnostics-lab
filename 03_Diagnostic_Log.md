# Diagnostic Log
## Mac Computer Diagnostics and IT Support Lab

**Project ID:** APLUS-LAB-001

## Purpose

This log records the diagnostic tests performed, the commands or tools used, the actual results, and the conclusions.

## Test Record Template

#Test 001: Identify Mac Hardware and Operating System

## Test ID:
**Test Date:**
**Test Name:**
**Purpose:**
**Tool or Command Used:**
**Expected Result:**
**Actual Result:**
**Interpretation:**
**Status:** Not started
**Notes:**

---

## Diagnostic Test Records

No diagnostic tests have been performed yet.


## Test 001: Identify Mac Hardware and Operating System

**Test ID:** APLUS-TEST-001

**Test Date:** October 27, 2026

**Test Name:** System Identification

**Purpose:** Identify the computer model, processor, and operating system version.

**Tool or Command Used:** Apple menu () → About This Mac

**Expected Result:** The Mac model, chip, and macOS version should be displayed.



**Actual Result:**
- Mac Model: MacBook Pro (16-inch, 2023)
- Chip: Apple M2 Pro
- Operating System: macOS Sequoia 15.6.1

**Interpretation:** The system identification information was successfully located. This test confirms the displayed hardware and operating system details; it does not establish whether the computer has any hardware problems.

**Status:** Completed

**Notes:** No settings were changed during this test.

---

## Test 002: Check Storage Capacity and Usage

**Test ID:** APLUS-TEST-002

**Test Date:** October 28, 2026

**Test Name:** Storage Inspection

**Purpose:** Check total storage capacity and determine how much storage is used and available.

**Tool Used:** System Settings → General → Storage

**Expected Result:** Storage capacity and usage information should be displayed.

**Actual Result:**
- Total storage displayed: 994.66 GB
- Used storage displayed: 286.6 GB
- Available storage calculated: 708.06 GB

**Interpretation:** Approximately 28.8% of the displayed storage is used, and 71.2% is available based on the reported figures. These numbers alone do not indicate a storage problem.

**Status:** Completed

**Notes:** Available storage was calculated by subtracting used storage from total storage. No files were deleted and no settings were changed.

---



## Test 003: Identify Installed Memory (RAM)

**Test ID:** APLUS-TEST-003

**Test Date:** October 28, 2026

**Test Name:** Installed Memory Inspection

**Purpose:** Identify the amount of RAM installed in the computer.

**Tool Used:** Apple menu () → About This Mac

**Expected Result:** The installed memory amount should be displayed.

**Actual Result:**
- Installed Memory: 16 GB
- Processor: Apple M2 Pro

**Interpretation:** The Mac reports 16 GB of installed memory. This test confirms the displayed memory capacity; it does not measure memory performance or establish whether a memory problem exists.

**Status:** Completed

**Notes:** No settings were changed during this test.

---


## Test 003: Identify Installed Memory (RAM)

**Test ID:** APLUS-TEST-003

**Test Date:** October 28, 2026

**Test Name:** Installed Memory Inspection

**Purpose:** Identify the amount of RAM installed in the computer.

**Tool Used:** Apple menu () → About This Mac

**Expected Result:** The installed memory amount should be displayed.

**Actual Result:**
- Installed Memory: 16 GB
- Processor: Apple M2 Pro

**Interpretation:** The Mac reports 16 GB of installed memory. This test confirms the displayed memory capacity; it does not measure memory performance or establish whether a memory problem exists.

**Status:** Completed

**Notes:** No settings were changed during this test.

---


## Test 004: Collect macOS System Information

**Test ID:** APLUS-TEST-004

**Test Date:** October 28, 2026

**Test Name:** Operating System Version and Build Identification

**Purpose:** Identify the installed macOS version and build number using a command-line tool.

**Tool or Command Used:** Terminal — `sw_vers`

**Expected Result:** The command should display the macOS product name, version, and build number.

**Actual Result:**
- Product Name: macOS
- Product Version: 15.6.1
- Build Version: 24G90

**Interpretation:** The command successfully returned the operating system's version and build information. This confirms system identification details but does not test the overall health or security of macOS.

**Status:** Completed

**Notes:** The command only displayed information and did not change system settings or files.

---


### Test 005: Identify Network Interfaces

**Date:** October 28, 2026

**Objective:** Identify the Mac's network interfaces.

**Tool:** Terminal

**Command:** `networksetup -listallhardwareports`

**Results:**
- Wi-Fi interface identified as `en0`.
- Several Ethernet and Thunderbolt network interfaces were listed.
- The Mac was connected to Wi-Fi during the test.

**Interpretation:** macOS recognizes the Wi-Fi network interface. The command identifies available network interfaces but does not independently verify internet connectivity or network performance.

**Status:** Completed

**Changes made:** None. Read-only inspection only.

**Privacy note:** MAC addresses were excluded from the project record.




### Test 006: Check the Wi-Fi IPv4 Address

**Date:** October 29, 2026

**Objective:** Identify the IPv4 address assigned to the Mac's Wi-Fi interface.

**Tool:** Terminal

**Command:** `ipconfig getifaddr en0`

**Result:** `[REDACTED_PRIVATE_IP]`

**Interpretation:** The Mac has a private IPv4 address assigned to its Wi-Fi interface. This is consistent with the Mac having an address on a local network. This test does not independently verify internet connectivity.

**Status:** Completed

**Changes made:** None. Read-only inspection only.

**Privacy note:** This is a private IP address. Avoid publishing network details unnecessarily.



### Test 007: Identify the Default Gateway

**Date:** October 29, 2026

**Objective:** Identify the default gateway used by the Mac.

**Tool:** Terminal

**Command:** `route -n get default`

**Results:**
- Default gateway: `[REDACTED_PRIVATE_IP]`
- Network interface: `en0`

**Interpretation:** The Mac's routing table identifies `[REDACTED_PRIVATE_IP]` as the default gateway. It is likely the local Wi-Fi router. This command identifies the configured route but does not independently confirm internet connectivity.

**Status:** Completed

**Changes made:** None. Read-only inspection only.



### Test 008: Test Connectivity to the Default Gateway

**Date:** October 29, 2026

**Objective:** Verify that the Mac can communicate with its default gateway.

**Tool:** Terminal

**Command:** `ping -c 4 [REDACTED_PRIVATE_IP]`

**Results:**
- Packets transmitted: 4
- Packets received: 4
- Packet loss: 0%
- Average round-trip time: 9.840 ms

**Interpretation:** The Mac successfully received replies from the default gateway during the test. No packet loss occurred in these four attempts. This result does not independently verify internet access.

**Status:** Completed

**Changes made:** None. Network connectivity test only.




### Test 009: Test Connectivity to a Public IP Address

**Date:** October 29, 2026

**Objective:** Check whether the Mac can reach a public internet address.

**Tool:** Terminal

**Command:** `ping -c 4 8.8.8.8`

**Results:**
- Destination: `8.8.8.8` (Google Public DNS)
- Packets transmitted: 4
- Packets received: 4
- Packet loss: 0%
- Average round-trip time: 26.206 ms

**Interpretation:** The Mac successfully received replies from a public IP address. This confirms reachability to that destination during the test, but does not verify every internet service or website.

**Status:** Completed

**Changes made:** None. Network connectivity test only.







### Test 010: Check DNS Name Resolution

**Date:** October 29, 2026

**Objective:** Verify that the Mac can resolve a domain name into IP addresses using DNS.

**Tool:** Terminal

**Command:** `nslookup google.com`

**Results:**
- DNS server queried: `[REDACTED_PRIVATE_IP]`
- Domain queried: `google.com`
- Multiple IP addresses were returned.
- The response was labeled non-authoritative.

**Interpretation:** DNS name resolution succeeded for `google.com`. The DNS server returned multiple IP addresses for the domain. This test does not independently verify that a web browser can load the website.

**Status:** Completed

**Changes made:** None. Read-only DNS lookup.

### Test 011: List Network Services and Order

**Date:** October 29, 2026

**Objective:** Identify the network services configured on the Mac and view their listed order.

**Tool:** Terminal

**Command:** `networksetup -listnetworkserviceorder`

**Results:**
- USB 10/100/1000 LAN — `en7`
- Thunderbolt Bridge — `bridge0`
- Wi-Fi — `en0`
- iPhone USB — `en8`

**Interpretation:** macOS lists four network services. This command displays their configured service order but does not confirm which service is currently carrying network traffic.

**Status:** Completed

**Changes made:** None. Read-only inspection.

**Additional verification:** The command `route -n get default` showed gateway `[REDACTED_PRIVATE_IP]` and interface `en0`. This indicates that Wi-Fi is the interface used for the Mac's default route at the time of testing.




### Test 012: Inspect DNS Configuration

**Date:** October 29, 2026

**Objective:** Inspect the DNS resolver configuration used by macOS.

**Tool:** Terminal

**Command:** `scutil --dns`

**Results:**
- DNS servers listed: `[REDACTED_PRIVATE_IP]`, `[REDACTED_PRIVATE_IP]`, and `[REDACTED_PRIVATE_IP]`
- Resolver interface: `en0` (Wi-Fi)
- Resolver reachability status: Reachable

**Interpretation:** macOS lists three DNS servers for this resolver, associated with the Wi-Fi interface. The first server matches the DNS server reported by `nslookup` in Test 010. The reachability status does not independently prove that every DNS query will succeed.

**Status:** Completed

**Changes made:** None. Read-only inspection.




Test ID: 001
Test Date: October 2026
Test Name: Identify Mac Hardware and Operating System
Purpose: Identify the computer model, processor, and operating system.
Tool or Command Used: Apple menu → About This Mac
Expected Result: The Mac displays its model, processor, and macOS version.
Actual Result: MacBook Pro (16-inch, 2023), Apple M2 Pro, macOS Sequoia 15.6.1.
Interpretation: The system information was displayed successfully.
Status: Completed
Notes: Read-only inspection. No settings were changed.



## Test 002: Check Storage Capacity

**Test ID:** 002  
**Test Date:** October 2026  
**Test Name:** Check Storage Capacity and Usage  
**Purpose:** Check how much storage is used and how much remains available.  
**Tool or Command Used:** System Settings → General → Storage  
**Expected Result:** macOS displays storage usage information.  
**Actual Result:** 286.6 GB used out of 994.66 GB displayed.  
**Interpretation:** Approximately 708.06 GB remained by subtraction. This is an estimate based on the displayed total and used space.  
**Status:** Completed  
**Notes:** Read-only inspection. No files were deleted.

## Test 003: Check Installed Memory

**Test ID:** 003  
**Test Date:** October 2026  
**Test Name:** Check Installed Memory  
**Purpose:** Identify the amount of installed RAM.  
**Tool or Command Used:** Apple menu → About This Mac  
**Expected Result:** macOS displays the installed memory amount.  
**Actual Result:** 16 GB RAM; Apple M2 Pro processor.  
**Interpretation:** The system reports 16 GB of installed memory. This check does not test memory performance or prove that RAM is fault-free.  
**Status:** Completed  
**Notes:** Read-only inspection.

## Test 004: Check macOS Version and Build

**Test ID:** 004  
**Test Date:** October 2026  
**Test Name:** Check Operating System Version  
**Purpose:** Record the installed macOS version and build number.  
**Tool or Command Used:** Terminal command `sw_vers`  
**Expected Result:** Terminal displays the operating system name, version, and build.  
**Actual Result:** macOS Sequoia 15.6.1, build 24G90.  
**Interpretation:** The installed operating system version and build were identified successfully.  
**Status:** Completed  
**Notes:** Read-only command. No system settings were changed.



## Test 005: Identify Network Interfaces

**Test ID:** 005  
**Test Date:** October 2026  
**Test Name:** Identify Network Interfaces  
**Purpose:** Identify the network interfaces available on the Mac.  
**Tool or Command Used:** Terminal command `networksetup -listallhardwareports`  
**Expected Result:** Terminal lists the available network hardware ports and their interfaces.  
**Actual Result:** Wi-Fi was listed as interface `en0`. Other interfaces, including Ethernet and Thunderbolt interfaces, were also listed.  
**Interpretation:** The Mac has multiple listed network interfaces. Wi-Fi was identified as `en0`.  
**Status:** Completed  
**Notes:** MAC addresses are intentionally omitted to protect privacy.

## Test 006: Check Wi-Fi IPv4 Address

**Test ID:** 006  
**Test Date:** October 2026  
**Test Name:** Identify Wi-Fi IPv4 Address  
**Purpose:** Find the IPv4 address assigned to the Wi-Fi interface.  
**Tool or Command Used:** Terminal command `ipconfig getifaddr en0`  
**Expected Result:** Terminal displays the IPv4 address assigned to `en0`.  
**Actual Result:** `[REDACTED_PRIVATE_IP]`  
**Interpretation:** The Mac had a private IPv4 address assigned to its Wi-Fi interface at the time of testing.  
**Status:** Completed  
**Notes:** The address may change depending on network and DHCP settings.

## Test 007: Identify Default Gateway

**Test ID:** 007  
**Test Date:** October 2026  
**Test Name:** Identify Default Gateway  
**Purpose:** Identify the gateway used for traffic leaving the local network.  
**Tool or Command Used:** Terminal command `route -n get default`  
**Expected Result:** Terminal displays the default route and its gateway.  
**Actual Result:** Gateway `[REDACTED_PRIVATE_IP]`; interface `en0`.  
**Interpretation:** The default route used gateway `[REDACTED_PRIVATE_IP]` through Wi-Fi at the time of testing.  
**Status:** Completed  
**Notes:** The gateway is commonly the local router on a home or apartment network.

## Test 008: Test Connectivity to Default

## Test 009: Test Connectivity to a Public IP Address

**Test ID:** 009  
**Test Date:** October 2026  
**Test Name:** Ping Public IP Address  
**Purpose:** Check whether the Mac can reach a public IP address.  
**Tool or Command Used:** Terminal command `ping -c 4 8.8.8.8`  
**Expected Result:** The public IP address responds to ping requests.  
**Actual Result:** 4 packets transmitted, 4 received, 0% packet loss; average round-trip time approximately 26.206 ms.  
**Interpretation:** The Mac successfully reached `8.8.8.8` during this test. This does not guarantee that every website or internet service is accessible.  
**Status:** Completed  
**Notes:** `8.8.8.8` is a public IP address operated by Google.

## Test 010: Test DNS Name Resolution

**Test ID:** 010  
**Test Date:** October 2026  
**Test Name:** DNS Lookup  
**Purpose:** Check whether a domain name can be resolved to IP addresses.  
**Tool or Command Used:** Terminal command `nslookup google.com`  
**Expected Result:** The DNS lookup returns IP addresses for the requested domain.  
**Actual Result:** The lookup returned multiple IP addresses for `google.com`. The DNS server displayed was `[REDACTED_PRIVATE_IP]`.  
**Interpretation:** DNS resolution succeeded for `google.com` during this test.  
**Status:** Completed  
**Notes:** A “Non-authoritative answer” is normal for this type of lookup.

## Test 011: Review Network Service Order

**Test ID:** 011  
**Test Date:** October 2026  
**Test Name:** List Network Services and Order  
**Purpose:** Review the configured network services and identify the interface used by the default route.  
**Tool or Command Used:** Terminal commands `networksetup -listnetworkserviceorder` and `route -n get default`  
**Expected Result:** Terminal lists network services and the default route.  
**Actual Result:** The listed services included USB Ethernet, Thunderbolt Bridge, Wi-Fi, and iPhone USB. The default route used gateway `[REDACTED_PRIVATE_IP]` through interface `en0`.  
**Interpretation:** Wi-Fi was the interface used by the default route at the time of testing. The service list alone does not establish which interface carries all network traffic.  
**Status:** Completed  
**Notes:** Service availability and routing can change when connections change.

## Test 012: Inspect DNS Configuration

**Test ID:** 012  
**Test Date:** October 2026  
**Test Name:** Inspect DNS Configuration  
**Purpose:** Review the DNS servers configured in macOS.  
**Tool or Command Used:** Terminal command `scutil --dns`  
**Expected Result:** Terminal displays DNS resolver information and configured name servers.  
**Actual Result:** The Wi-Fi resolver listed DNS servers `[REDACTED_PRIVATE_IP]`, `[REDACTED_PRIVATE_IP]`, and `[REDACTED_PRIVATE_IP]`. The resolver was marked reachable.  
**Interpretation:** macOS listed DNS servers for the Wi-Fi resolver. The earlier DNS lookup also succeeded. The resolver's reachability status alone does not guarantee that every DNS query will succeed.  
**Status:** Completed  
**Notes:** DNS configuration can vary with network settings.













