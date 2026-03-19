# Task 2: Document Security Events

## Objective
To simulate SOC event documentation using a structured logging format.

---

## Tools Used
- Kali Linux Terminal
- Nano Editor
- System Logs (/var/log/auth.log)

---

## Commands Used

```bash
mkdir SOC_Task2
cd SOC_Task2
nano security_events.log
cat security_events.log
sudo grep "Failed password" /var/log/auth.log
ssh fakeuser@localhost
