# Assignment 1 – Transliteration Accuracy Testing

**STUDENT INFORMATION**

Student Name: Gunasekara A G A G D
Registration Number: IT23543478
Course: IT3040 - ITPM
Assignment: Assignment 1 - Year 3 Semester 1


**IT3040 – ITPM | Year 3 Semester 1 | Option 1**

Automated testing of the Chat Sinhala transliteration function at [https://www.pixelssuite.com/chat-translator](https://www.pixelssuite.com/chat-translator) using Playwright.

---

## Prerequisites

- Python 3.11 or Up version     (You must have python installed on your pc)
- Google Chrome (recommended) — or let Playwright install Chromium automatically
- Git `                         (You must have Git installed on your pc)
---

## Setup Instructions

### 1. Clone repo

```bash
git clone https://github.com/Gimantha-Dil/IT23543478_project_playwright.git
```
### 2. Dependencies run (one time)

```bash
python -m pip install -U pip 
python -m pip install playwright openpyxl
python -m playwright install
```
**or**

```bash
py -m pip install -U pip 
py -m pip install playwright openpyxl
py -m playwright install
```

### 3. Running the Tests

Then run it from inside the `IT23543478_project_playwright` folder:

```bash
python test_automation.py --excel "Assignment 1 - Test cases.xlsx" --url "https://www.pixelssuite.com/chat-translator" --wait-ms 5000 --type-delay-ms 80 --slow-mo-ms 200 --save-every 1 --keep-open
```
**or**

```bash
py test_automation.py --excel "Assignment 1 - Test cases.xlsx" --url "https://www.pixelssuite.com/chat-translator" --wait-ms 5000 --type-delay-ms 80 --slow-mo-ms 200 --save-every 1 --keep-open
```

### Command line arguments

| Argument          | Description                                   | Default                                       | 
|-------------------|-----------------------------------------------|-----------------------------------------------| 
| `--excel`         | Path to excel test cases file                 | Auto-detected                                 | 
| `--url`           | URL of the application under test             | `https://www.pixelssuite.com/chat-translator` | 
| `--wait-ms`       | Wait time (ms) after each transliteration     | `5000`                                        | 
| `--type-delay-ms` | Delay (ms) between each typed character       | `80`                                          | 
| `--slow-mo-ms`    | Slow motion delay (ms) for Playwright actions | `200`                                         | 
| `--save-every`    | Save excel after every N rows                 | `0` (save at end)                             | 
| `--keep-open`     | Keep browser open after tests finish          | `false`                                       | 
| `--headless`      | Run browser in headless mode (no UI)          | `false`                                       |

---

## Project Structure

```
IT23543478__project_-playwright/

├── Assignment 1 - Test cases.xlsx  # Test cases with inputs, expected & actual outputs
├── README.md                       # This file
├── test_automation.py              # Main Playwright automation script
```

---

## Structure of Excel File

The `Assignment 1 - Test cases.xlsx` file contains the following columns:

| Column                                           | Description                                            |
|--------------------------------------------------|--------------------------------------------------------|
| TC ID                                            | Test case ID (all negative cases start with `Neg_`)    | 
| Input length type                                | S (≤30 chars), M (31–299 chars), or L (300–450 chars)  | 
| Input                                            | Singlish (chat-style romanised Sinhala) input          | 
| Expected output                                  | Correct Sinhala transliteration                        | 
| Actual output                                    | Auto-filled by the script after execution              | 
| Status                                           | Auto-filled: `PASS`, `FAIL`, or `COLLECTED`            | 
| Singlish input types covered                     | Singlish input categories covered by the test case     | 
| Evidence or rationale for the input type covered | Justification for the input type classification        |

---

## Test Coverage

50 negative test cases for all 24 types of Singlish input defined in Appendix 1 (at least 2 for each type):

1) Question forms
2) Command forms
3) Greetings
4) Requests
5) Responses
6) Repeated Words
7) Inputs with Punctuation Marks
8) Romanization / Spelling Variants
9) Isolated English Word Insertions in Singlish
10) Multi-Word English Phrases in Singlish
11) English Digital Terms in Singlish
12) Platform/App Names in Singlish
13) English Abbreviations/Acronyms in Singlish
14) English Clipped Forms in Singlish
15) Place Names Embedded in Singlish
16) Person Names Embedded in Singlish
17) Inputs with Numbers and Numeric Suffixes
18) Inputs with Currency
19) Inputs with Time Formats
20) Inputs with Dates
21) Inputs with Unit of Measurements
22) Inputs with Slang and Casual Phrasing
23) Online Identifiers in Singlish
24) Inputs Containing Emojis

---

## Notes

- Do **not** manually edit the `Actual output` or `Status` columns — they are filled automatically by the script.

