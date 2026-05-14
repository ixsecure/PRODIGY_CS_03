# Password Strength Checker

![Language](https://img.shields.io/badge/Language-Python-3776AB?style=flat&logo=python&logoColor=white)
![Type](https://img.shields.io/badge/Type-Security%20Tool-red?style=flat)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=flat)
![Internship](https://img.shields.io/badge/Internship-Prodigy%20InfoTech-blue?style=flat)

> Python tool that evaluates password strength based on 5 essential security criteria and returns a score with actionable feedback.

---

## About

This project is a cybersecurity analysis tool developed in Python as part of the **Prodigy InfoTech** internship program (Task 03). It evaluates the strength of a password by testing five essential security criteria and returns a clear security level with improvement recommendations.

---

## How it works

The program assigns a score from 0 to 5 by verifying:

| Criteria | Rule | Why it matters |
|---|---|---|
| Length | At least 8 characters | Resists brute-force attacks |
| Uppercase | At least 1 uppercase letter | Increases character space |
| Lowercase | At least 1 lowercase letter | Avoids all-caps weakness |
| Numbers | At least 1 digit (0-9) | Adds numeric complexity |
| Special characters | At least 1 symbol (!@#$%^&*) | Strongest entropy boost |

---

## Security Levels

| Score | Level | Verdict |
|---|---|---|
| 0 - 1 / 5 | Very Weak | Dangerous — change immediately |
| 2 / 5 | Weak | Easy to crack |
| 3 / 5 | Medium | Acceptable but improvable |
| 4 / 5 | Strong | Good password |
| 5 / 5 | Very Strong | Excellent — all criteria met |

---

## Usage

```bash
# Clone the repo
git clone https://github.com/ixsecure/PRODIGY_CS_03.git
cd PRODIGY_CS_03

# Run the tool
python password_checker.py
```

```
Enter your password: MyP@ssw0rd!

Criteria check:
  [+] Length        : OK (10 characters)
  [+] Uppercase     : OK
  [+] Lowercase     : OK
  [+] Numbers       : OK
  [+] Special chars : OK

Score  : 5 / 5
Level  : Very Strong — Excellent
```

---

## Code

```python
import re

def check_password_strength(password):
    score = 0
    feedback = []

    if len(password) >= 8:
        score += 1
    else:
        feedback.append("Use at least 8 characters")

    if re.search(r'[A-Z]', password):
        score += 1
    else:
        feedback.append("Add at least one uppercase letter")

    if re.search(r'[a-z]', password):
        score += 1
    else:
        feedback.append("Add at least one lowercase letter")

    if re.search(r'\d', password):
        score += 1
    else:
        feedback.append("Add at least one number")

    if re.search(r'[!@#$%^&*(),.?":{}|<>]', password):
        score += 1
    else:
        feedback.append("Add at least one special character (!@#$%^&*)")

    levels = {
        0: "Very Weak   — Dangerous",
        1: "Very Weak   — Dangerous",
        2: "Weak        — Easy to crack",
        3: "Medium      — Acceptable",
        4: "Strong      — Good password",
        5: "Very Strong — Excellent"
    }

    print(f"\nScore : {score} / 5")
    print(f"Level : {levels[score]}")

    if feedback:
        print("\nTo improve:")
        for tip in feedback:
            print(f"  - {tip}")

password = input("Enter your password: ")
check_password_strength(password)
```

---

## What I learned

- Using Python `re` module for pattern matching and regex
- Translating security rules into executable code
- Building a scoring system with conditional logic
- Providing actionable user feedback — not just a score
- Understanding why each password criterion matters from an attacker's perspective

---

## Author

**Richmond Konan** — Junior Penetration Tester | Offensive Security | Cote d'Ivoire

- LinkedIn: https://linkedin.com/in/richmonddelmas
- GitHub: https://github.com/ixsecure
- Email: delmasrichmond@gmail.com

---

## Topics

`python` `cybersecurity` `password-security` `security-tool` `penetration-testing` `prodigy-infotech` `internship` `regex` `brute-force-prevention`
