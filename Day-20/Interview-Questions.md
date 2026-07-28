# Day 20 - MITRE ATT&CK Framework Interview Questions

## Q1. What is MITRE ATT&CK?

Answer:

MITRE ATT&CK is a knowledge base of real-world attacker behaviors organized into tactics, techniques, and procedures (TTPs). It helps security teams detect, investigate, and respond to cyber attacks.

---

## Q2. What does ATT&CK stand for?

Answer:

Adversarial Tactics, Techniques & Common Knowledge.

---

## Q3. Who developed MITRE ATT&CK?

Answer:

MITRE Corporation.

---

## Q4. Why is MITRE ATT&CK important for SOC analysts?

Answer:

- Understand attacker behavior
- Map alerts to ATT&CK techniques
- Improve detection rules
- Perform threat hunting
- Enhance incident response

---

## Q5. Difference between Tactic and Technique?

Answer:

Tactic = Attacker's goal.

Technique = How the attacker achieves that goal.

---

## Q6. What is a Sub-technique?

Answer:

A more detailed implementation of a technique.

Example:

PowerShell → Encoded Commands.

---

## Q7. What is Detection in ATT&CK?

Answer:

Detection describes how defenders can identify a specific attack technique using logs, SIEM, Sysmon, or EDR.

---

## Q8. What is Mitigation?

Answer:

Mitigation refers to security controls that reduce or prevent attacker techniques.

Examples:

- MFA
- Patch Management
- Application Control

---

## Q9. Name any six ATT&CK tactics.

Answer:

- Initial Access
- Execution
- Persistence
- Privilege Escalation
- Credential Access
- Lateral Movement

---

## Q10. Explain Initial Access.

Answer:

Initial Access is the tactic attackers use to gain entry into a target system.

Examples:

- Phishing
- Drive-by Compromise
- Exploiting Public-Facing Applications

---

## Q11. Explain Execution.

Answer:

Execution involves running malicious code on a victim's system.

Example:

PowerShell (T1059.001)

---

## Q12. Explain Persistence.

Answer:

Persistence allows attackers to maintain access even after reboot.

Examples:

- Registry Run Keys
- Scheduled Tasks
- Services

---

## Q13. How is MITRE ATT&CK used in SIEM?

Answer:

SIEM maps alerts to ATT&CK techniques, helping analysts understand attacker behavior and prioritize investigations.

---

## Q14. How is MITRE ATT&CK used in Threat Hunting?

Answer:

Threat hunters use ATT&CK techniques as hypotheses and search logs for evidence of attacker behavior.

---

## Q15. Difference between MITRE ATT&CK and Cyber Kill Chain?

Answer:

Cyber Kill Chain describes attack phases in a linear sequence, while MITRE ATT&CK provides a detailed, real-world mapping of attacker tactics and techniques and is more practical for SOC operations.