# Assignment 1 - Singlish to Sinhala Transliteration Testing

**Module:** IT3040 – IT Project Management  
**Year:** 3 | **Semester:** 2 
**Student:** IT23243576 

---

## Overview

This project automates testing of the **Chat Sinhala transliteration** function at:  
https://www.pixelssuite.com/chat-translator

The script uses **Playwright** to open a real browser, type each Singlish test case into the input field, click the Transliterate button, capture the actual output from the API response, and record the result (PASS/FAIL) in the Excel file.

A total of **50 negative test cases** are tested, covering all 24 Singlish input types defined in the assignment.

---

## Prerequisites

- Python 3.11 or 3.12 — https://www.python.org/downloads/
- Google Chrome (recommended) — https://www.google.com/chrome/
- Windows OS

---

## Installation (One-Time Setup)

**Step 1 — Clone or download this repository**

```
git clone <your-repo-url>
```
Or download and extract the ZIP file.

**Step 2 — Open Command Prompt and navigate to the project folder**

```
cd path\to\IT23243576
```

**Step 3 — Install required Python packages**

```
pip install -U pip
pip install playwright openpyxl
```

**Step 4 — Install Playwright browsers**

```
playwright install
```

---

## How to Run the Tests

Open Command Prompt, navigate to the project folder, and run:

```
python test_automation.py --excel "Assignment_1_Test_Cases.xlsx" --sheet "Assignment 1 Test Cases" --url "https://www.pixelssuite.com/chat-translator" --wait-ms 20000 --type-delay-ms 80 --slow-mo-ms 200 --save-every 1
```

**What happens when you run it:**
- A Chrome browser window opens automatically
- The script loads the chat-translator page
- Each test case input is typed into the input field
- The Transliterate button is clicked
- The actual output is captured from the API response
- Results are saved to the Excel file after every row
- The browser closes when all 50 rows are done

**Expected runtime:** approximately 12–15 minutes (the API takes ~15 seconds per request)

---

## Command Arguments Explained

| Argument | Value | Description |
|---|---|---|
| --excel | Assignment_1_Test_Cases.xlsx | Path to the Excel test cases file |
| --sheet | "Assignment 1 Test Cases" | Sheet name inside the Excel file |
| --url | https://www.pixelssuite.com/chat-translator | URL of the application under test |
| --wait-ms | 20000 | Max wait time (ms) for API response per row |
| --type-delay-ms | 80 | Delay between keystrokes (ms) to simulate human typing |
| --slow-mo-ms | 200 | Slow motion delay for browser actions (ms) |
| --save-every | 1 | Save Excel after every 1 row |

---

## Checking Results

After the script finishes, open `Assignment_1_Test_Cases.xlsx`:

- **Actual output** column — the Sinhala text returned by the application
- **Status** column — PASS if actual output matches expected output exactly, FAIL otherwise

---

## Project Structure

```
IT23243576/
├── test_automation.py            # Main Playwright automation script
├── Assignment_1_Test_Cases.xlsx  # Test cases (input, expected, actual, status)
└── README.md                     # This file
```

---

## Troubleshooting

**Excel permission error** — Make sure the Excel file is closed before running the script.

**Browser not found** — Install Google Chrome or run `playwright install chromium` to use the bundled browser.

**Empty actual output** — The API occasionally times out. Re-run the script; it will overwrite previous results.

**Python not found** — Make sure Python 3.11/3.12 is installed and added to your system PATH.
