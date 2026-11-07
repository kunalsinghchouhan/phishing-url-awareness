# EWB Phishing URL Awareness Checker

## Overview

Phishing is a cyberattack in which attackers use fake links or messages to trick people into sharing sensitive information such as passwords, banking details, or OTPs.

The EWB Phishing URL Awareness Checker is a Python-based educational tool that examines URL text and identifies common phishing warning signs. It helps users become more aware of suspicious URL characteristics without visiting the website.

## Features

- Detects an `@` symbol in the URL.
- Flags unusually long URLs (over 100 characters).
- Flags IP-address hostnames.
- Flags many hostname segments (5 or more).
- Flags punycode-style hostnames (`xn--`).
- Flags the HTTP scheme.
- Allows users to inspect multiple URLs in one session.
- Displays a **REVIEW CAREFULLY** summary when warning signs are detected.
- Handles malformed URL input without crashing.
- Provides a quit option to exit the program.

## Requirements

- Python 3.10 or later.
- No extra packages required.
- Uses only Python's built-in libraries.

## How to Run

1. Download or clone this repository.
2. Open the project folder in VS Code or a terminal.
3. Run the following command:

**Windows:**
```bash
python phishing_checker.py
```

**Mac/Linux:**
```bash
python3 phishing_checker.py
```

4. Enter a sample URL when prompted.
5. Type `q` to quit the program.

## Example Output

```text
==================================================
       EWB PHISHING URL AWARENESS CHECKER
==================================================
Text checks only - this program does not open URLs.
Enter 'q' to quit.

Enter a sample URL: http://192.0.2.10/account

Result:
- Uses an IP address instead of a familiar domain.
- Uses HTTP. HTTPS alone does not prove trust.

REVIEW CAREFULLY: 2 warning sign(s) found.

Remember: Warning signs are clues, not proof.
Never enter passwords from unexpected links.
```

## Testing

The project is tested using five sample URLs provided in the workbook.

| # | Input | Expected Result | Actual Result | Status |
|---|---|---|---|---|
| 1 | `https://www.example.com/login` | No warning signs | No listed warning signs found | Pass* |
| 2 | `http://192.0.2.10/account` | IP address + HTTP | IP address + HTTP warnings | Pass* |
| 3 | `http://example.com@sample.invalid/login` | @ symbol + HTTP | @ symbol + HTTP warnings | Pass* |
| 4 | `https://a.b.c.d.e.example.invalid/path` | Many hostname segments | Many hostname segments warning | Pass* |
| 5 | `https://xn--example.invalid/` | Punycode-style hostname | Punycode-style hostname warning | Pass* |

Full test evidence is available in `tests/test_samples.md`.

*Confirm these statuses against your actual terminal output.*

## Screenshots

### Sample Program Run
<img width="1240" height="403" alt="sample_run" src="https://github.com/user-attachments/assets/c4831bca-1123-4ec2-98c6-eb4886bc5a56" />


### Test Results
<img width="1302" height="456" alt="test_results" src="https://github.com/user-attachments/assets/f92f4861-4a58-4b67-b85e-e4082d3fe323" />


## Improvements

1. **Multiple URL Checking:** Added a loop that allows users to inspect multiple URLs without restarting the program. A quit option (`q`) allows users to exit.

2. **Warning Summary:** Added a `REVIEW CAREFULLY` message that displays the number of warning signs detected for a URL.

3. **Malformed URL Handling:** Added exception handling using `try-except` to prevent the program from crashing when an incorrectly formatted URL is entered.

All improvements should be checked again using the workbook's test cases.

## Limitations

This is an educational tool. It only reads URL text and checks for selected warning signs.

- It does not visit URLs.
- It does not scan websites for malware.
- It does not use online reputation services.
- It cannot guarantee whether a URL is safe or malicious.

**No warning signs found does NOT mean a URL is safe.**

## Ethical Use

- Use sample URL strings only.
- Do not collect passwords, OTPs, or other credentials.
- Do not use this project to deceive anyone.
- Do not test or probe websites without permission.

This project is intended for defensive cybersecurity awareness and educational purposes only.

## Author

**Name:** Kunal Singh Chouhan 
**Course:** B.Tech Information Technology  
**Batch:** 2023-2027 
**Organization:** EWB Courses
