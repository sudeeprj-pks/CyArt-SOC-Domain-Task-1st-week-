# Incident Report – DDoS Attack

## 1. Incident Summary
- Incident ID: SOC-2026-001
- Date: [Add Today Date]
- Analyst: Sudeep
- Severity: High
- Status: Resolved

## 2. Description
A Distributed Denial of Service (DDoS) attack caused high traffic on the web server leading to downtime.

## 3. Detection
- Tool: Simulated Logs / SIEM
- Alert: Traffic spike detected

## 4. Affected System
- Web Server (192.168.1.10)

## 5. IOCs
- Multiple IP requests
- SYN flood traffic

## 6. Actions Taken
- Blocked IPs
- Enabled rate limiting

## 7. Root Cause
No traffic filtering rules were configured.

## 8. Lessons Learned
Need proper firewall and monitoring setup.

## 9. Recommendation
Implement WAF and alert thresholds.
