# 🛡️ SOC Analyst Practical Task Report

## Task: Log Analysis & Browser History Investigation

---

# 🔴 1. Windows Log Analysis (Brute-Force Detection)

## 🎯 Objective

To identify failed login attempts and detect brute-force attack patterns using Windows Security logs.

---

## 🛠️ Tools Used

* Windows Event Viewer
* PowerShell (`Get-WinEvent`)
* Command Prompt (`wevtutil`)

---

## ⚙️ Procedure

### Step 1: Generate Failed Logins

* Multiple incorrect login attempts were performed on the system to simulate a brute-force attack.

---

### Step 2: Analyze Logs using PowerShell

Command used:

```
Get-WinEvent -FilterHashtable @{LogName='Security'; Id=4625}
```

---

### Step 3: Analyze Logs using CLI

Command used:

```
wevtutil qe Security /q:"*[System[(EventID=4625)]]" /f:text /c:50
```

---

### Step 4: Analyze Logs using Event Viewer

* Navigated to:
  `Windows Logs → Security`
* Applied filter for **Event ID 4625**

---

## 📊 Findings

* Multiple **failed login attempts (Event ID 4625)** detected
* Repeated timestamps indicate rapid login attempts
* Logon Type: **2 (Interactive login)**
* Source Network Address: **127.0.0.1**

👉 This confirms a **simulated brute-force attack scenario**

---

## 📸 Evidence

### 🔹 PowerShell Output

* Shows multiple failed login attempts
* Confirms Event ID 4625 detection

### 🔹 wevtutil Output

* Detailed log including:

  * Failure reason
  * Logon type
  * Source IP

### 🔹 Event Viewer

* Filtered view of Event ID 4625
* Timeline of repeated login failures

---

## 🧠 SOC Analysis

* Repeated failed attempts in short time = **Brute-force behavior**
* Localhost (127.0.0.1) indicates **internal simulation**
* In real SOC:

  * Would correlate with IP reputation
  * Block attacker IP
  * Alert incident response team

---

## ✅ Conclusion

The system successfully detected multiple failed login attempts, demonstrating how SOC analysts identify brute-force attacks using Windows logs.

---

# 🌐 2. Browser History Analysis

## 🎯 Objective

To analyze browser activity and identify visited URLs for investigation purposes.

---

## 🛠️ Tools Used

* BrowsingHistoryView (Nirsoft)

---

## ⚙️ Procedure

### Step 1: Generate Browser Activity

* Visited multiple websites including test URLs

---

### Step 2: Extract Browser History

* Ran BrowsingHistoryView tool
* Automatically parsed Chrome history

---

### Step 3: Analyze URLs

* Reviewed visited URLs
* Checked timestamps and visit counts

---

## 📊 Findings

* Multiple URLs extracted from Chrome history
* Includes:

  * Google login pages
  * YouTube
* Visit timestamps and counts recorded

👉 Demonstrates successful browser artifact extraction

---

## 📸 Evidence

* Tool output showing:

  * URL
  * Visit time
  * Visit count

---

## 🧠 SOC Analysis

* Analysts use browser history to:

  * Detect phishing attempts
  * Identify malicious domains
  * Track user activity

* In real SOC:

  * URLs are checked against threat intelligence feeds
  * Suspicious domains are flagged

---

## ⚠️ Tool Learning Note

* Initially attempted with **LECmd**
* Identified that it is used for `.lnk` files
* Switched to **BrowsingHistoryView** for correct analysis

👉 Demonstrates tool understanding and troubleshooting

---

## ✅ Conclusion

Browser history analysis successfully revealed user activity and demonstrates how SOC analysts investigate potential threats using forensic tools.

---

# 📋 Overall Outcome

✔ Successfully performed log analysis
✔ Detected brute-force attack patterns
✔ Extracted and analyzed browser history
✔ Used multiple tools and troubleshooting methods

---

# 🚀 Skills Gained

* Windows Event Log Analysis
* PowerShell log querying
* CLI-based log extraction
* Browser forensic analysis
* SOC investigation workflow

---
