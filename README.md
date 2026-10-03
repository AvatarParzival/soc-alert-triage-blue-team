# SOC Alert Triage & Blue Team Assessment

[![Blue Team](https://img.shields.io/badge/Domain-Blue%20Team%20%2F%20SOC-1F6FEB)](https://en.wikipedia.org/wiki/Blue_team_(computer_security))
[![TryHackMe](https://img.shields.io/badge/Platform-TryHackMe-212C42?logo=tryhackme)](https://tryhackme.com/)
[![BTLO](https://img.shields.io/badge/Platform-Blue%20Team%20Labs%20Online-0A0A0A)](https://blueteamlabs.online/)
[![MITRE ATT&CK](https://img.shields.io/badge/MITRE%20ATT%26CK-Enterprise-005A9C)](https://attack.mitre.org/)

A professional SOC analyst assessment covering alert monitoring, triage, log correlation, and incident reporting across TryHackMe and Blue Team Labs Online. All three required activities completed with **100% room scores** and a **15/15 BTLO challenge result** — producing two documented findings rated Low (operational) to High.

> **Core principle:** a sound triage process prevents both false positives (wasted analyst time) and missed true positives (undetected threats) — context is what separates the two.

## Final Report

📄 **[Read the complete SOC Assessment Report](AbdullahZubair_Week7_SOC_Assessment_Report.pdf)**

- **Student ID:** AQT-1203
- **Assessment type:** Authorised training-lab assessment (TryHackMe / BTLO)
- **Report date:** 28 September 2026
- **Prepared by:** Abdullah Zubair

## Project Objectives

1. Complete TryHackMe — SOC Fundamentals room (100%).
2. Complete TryHackMe — SOC L1 Alert Triage room (100%).
3. Complete Blue Team Labs Online — The Report II challenge (15/15).
4. Apply the 5-Ws triage methodology to live SIEM alerts.
5. Produce a professional SOC case report with verdicts, impact, and recommendations.

## Scope and Environment

| Activity | Platform | Result |
|---|---|---|
| SOC Fundamentals | TryHackMe | ✅ 100% completion |
| SOC L1 Alert Triage | TryHackMe | ✅ 100% completion |
| The Report II | Blue Team Labs Online | ✅ 15/15 questions correct |

## Findings

| ID | Title | Severity | Verdict |
|---|---|---|---|
| SOC-01 | Port scan from authorised Nessus scanner (10.0.0.8) | 🔵 Low (operational) | False Positive |
| SOC-02 | Double-extension malware delivery attempt (*.exe) | 🟠 High | True Positive |

SOC-01 illustrates the cost of alert fatigue — a High-severity SIEM trigger that was benign when context was applied. SOC-02 demonstrates that a lower-profile alert can represent a genuine malware delivery attempt, caught only through TTP-based detection.

## Triage Methodology (5-Ws)

| W | SOC-01 (False Positive) | SOC-02 (True Positive) |
|---|---|---|
| **What** | Port scan activity | Double-extension file delivery |
| **When** | June 12, 2024 — 17:24 | — |
| **Where** | Internal network | Endpoint |
| **Who** | Nessus scanner (10.0.0.8) | Unknown actor |
| **Why** | Authorised vulnerability assessment | Malicious payload delivery attempt |

## Screenshots

![TryHackMe SOC Fundamentals — 100% completion](screenshots/SOC%20L1.png)

![SOC Fundamentals Task 6 — 5-Ws answers correct, flag THM{000_INTRO_TO_SOC}](screenshots/SOC%20L1.2.png)

![Blue Team Labs Online — The Report II, 15/15 questions correct](screenshots/SOC%20L1.3.png)

![TryHackMe SOC L1 Alert Triage — 100% completion](screenshots/SOC%20L1.4.png)

![SOC L1 Alert Triage — all three triage flags obtained correctly](screenshots/Screenshot%202026-09-28%20022916.png)

![TryHackMe SIEM dashboard — five alerts closed with correct verdicts (TP ×2, FP ×3)](screenshots/Screenshot%202026-09-28%20023004.png)

![BTLO The Report II — challenge completed](screenshots/report%20II.png)

## Recommendations

- Whitelist authorised scanner IPs in SIEM suppression rules during scheduled scan windows to reduce false-positive volume
- Document all scheduled scanning in a change-management calendar visible to SOC analysts for immediate triage context
- Implement application whitelisting (WDAC / AppLocker) to block execution of double-extension files at the endpoint
- Enable EDR behavioural rules to alert and auto-quarantine on double-extension file-creation events
- Build TTP-based SIEM detection rules aligned to MITRE ATT&CK rather than relying on hash- or IP-based indicators
- Establish formal SIEM tuning cycles to keep false-positive rates below 10%

## Repository Structure

```text
.
├── README.md
├── AbdullahZubair_Week7_SOC_Assessment_Report.pdf
├── AbdullahZubair_Week7_SOC_Assessment_Report.docx
└── screenshots/
```

## Limitations

- All activity was performed in TryHackMe and BTLO authorised training environments using simulated SIEM data.
- Alert findings are based on guided lab scenarios and should not be generalised to production SOC environments.
- The SIEM used was a TryHackMe in-browser simulation and does not reflect any specific commercial SIEM platform.
- Risk ratings reflect analyst judgment against the specific lab context and simulated log data.

## Lessons Learned

- Context is the difference between a High-severity false positive and a missed true positive — asset inventory and change management data are essential to triage.
- TTP-based detection (Pyramid of Pain) is significantly more durable than indicator-based rules, which adversaries trivially change.
- Alert fatigue is a real operational risk; excessive false positives increase mean-time-to-detect genuine threats.
- Effective SOC design requires retaining the right data for the right period — not just ingesting everything.
- Closing an alert with a clear verdict and a documented improvement action is as important as reaching the correct verdict.

## Author

**Abdullah Zubair**  
- GitHub: [@AvatarParzival](https://github.com/AvatarParzival)
- LinkedIn: [Abdullah Zubair](https://www.linkedin.com/in/abdullahzubairr)
- Email: [abdullah69zubair@gmail.com](abdullah69zubair@gmail.com)

## Responsible Use

This repository is intended for educational, defensive-security and professional portfolio purposes. All activities were completed within authorised TryHackMe and Blue Team Labs Online training environments. Do not reproduce these techniques against real systems or infrastructure without explicit written authorisation.
