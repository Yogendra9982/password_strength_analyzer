# 🔐 Password Analyzer

A simple Bash-based Password Strength Analyzer that checks password security and provides a strength rating based on common password security standards.

## Features

* Password length analysis
* Uppercase letter detection
* Lowercase letter detection
* Number detection
* Special character detection
* Common password detection
* Password strength scoring
* Strong password suggestions

## Why This Project?

Weak passwords are one of the most common causes of account compromise. This tool helps users evaluate their passwords and encourages the use of stronger, more secure credentials.

## Requirements

* Linux, Unix, or macOS
* Bash Shell

## Installation

Clone the repository:

```bash
git clone https://github.com/Yogendra9982/password_strength_analyzer.git
cd password_strength_analyzer
```

Make the script executable:

```bash
chmod +x password-analyzer.sh
```

Run the script:

```bash
./password-analyzer.sh
```

## Password Rating

| Score | Strength |
| ----- | -------- |
| 0-2   | Weak     |
| 3-4   | Medium   |
| 5-6   | Strong   |

## Example Output

```text
======================================
     PASSWORD STRENGTH ANALYZER
======================================

[+] Good Length (12)
[+] Uppercase Found
[+] Lowercase Found
[+] Number Found
[+] Special Character Found

Score : 6/6
Strong Password
```

## Learning Objectives

This project demonstrates:

* Bash Scripting
* Regular Expressions
* Conditional Statements
* Arrays and Loops
* Basic Password Security Concepts

## Author

**Yogendra Samriya**

## License

This project is licensed under the MIT License.
