[README2.md](https://github.com/user-attachments/files/35167469/README2.md)
# Python Assignment 2

**Course coverage:** CO2 – Analyse control-flow constructs, string operations and functions to perform string manipulations.

## Student Details

* Name:Selva Raaghav S
* Register Number:1914260028
* Python version: Python 3.10 
* Libraries:Python standard library only (`time`, `re`, `functools`, and `io` where used)

## Project Overview

This repository contains the Python source code, test inputs, execution screenshots and analysis for Assignment 2 (Q1–Q7).

|Task|Topic|Main concepts|
|-|-|-|
|Q1|Decisions with Many Boundaries|`if`, `if-elif-else`, `match-case`, Boolean conditions|
|Q2|Loops that Count Attempts|`while`, `for`, `break`, `continue`, `pass`, loop `else`|
|Q3|Vehicle Registration Number Validator|String methods, indexing, slicing, validation|
|Q4|Building Long Text: `+` or `join()`?|String immutability, concatenation, `join()`, timing|
|Q5|Functions, Parameters and Scope|Parameters, return values, mutable defaults, local/global/nonlocal|
|Q6|Recursion and Its Limits|Recursion, memoisation, call counts, iterative solution|
|Q7|Diagnose, Redesign and Validate|Bottleneck analysis, redesign, validation and complexity|

## Folder Structure

```text
CSA08-<RegisterNumber>-Assignment2/
│
├── Task01/
│   └── Q1.py
├── Task02/
│   └── Q2.py
├── Task03/
│   └── Q3.py
├── Task04/
│   └── Q4.py
├── Task05/
│   └── Q5.py
├── Task06/
│   └── Q6.py
├── Task07/
│   └── Q7.py
├── Output\_Screenshots/
│   ├── Q1/
│   ├── Q2/
│   ├── Q3/
│   ├── Q4/
│   ├── Q5/
│   ├── Q6/
│   └── Q7/
├── Results/
│   ├── benchmark\_timings.csv
│   └── call\_counts.txt
└── README.md
```

## Requirements

* Python 3.10 or later is recommended because Q1 includes a `match-case` implementation.
* No third-party packages are required.
* Q4 uses `time.perf\_counter()` to measure elapsed time.
* Q6 uses `functools.lru\_cache` for memoisation.

## How to Run

Open a terminal in the repository folder and run each task separately:

```bash
python Task01/Q1.py
python Task02/Q2.py
python Task03/Q3.py
python Task04/Q4.py
python Task05/Q5.py
python Task06/Q6.py
python Task07/Q7.py
```

On systems where the Python 3 command is `python3`, use `python3` instead of `python`.

## Execution and Evidence

Every program must be executed on the student's computer. Save screenshots of the program and its output in the corresponding `Output\_Screenshots` subfolder.

### Required evidence

* **Q1:** Predictions for eight households; compare separate `if` statements with `if-elif-else`.
* **Q2:** Demonstrate correct OTP, wrong OTP, blank entry, and lockout behaviour. Also test the security-question condition.
* **Q3:** Test six registration inputs, including at least two invalid inputs. Show normalised and receipt formats.
* **Q4:** Run the timing test for 1,000, 10,000 and 200,000 lines. Run it three times and report averages.
* **Q5:** Show the mutable-default bug, corrected function, and independent orders for three customers.
* **Q6:** Record call counts for n = 10, 20, 25 and 30; test the memoised and iterative versions for n = 1,000.
* **Q7:** Compare the original and redesigned versions with the same input. Record actual elapsed times and verify equal results where both versions complete.

## Recording Benchmark Results

Do not enter estimated or invented execution times. Record the values measured on your own computer.

Suggested CSV format for `Results/benchmark\_timings.csv`:

```csv
lines,run,plus\_seconds,join\_seconds
1000,1,,
1000,2,,
1000,3,,
10000,1,,
10000,2,,
10000,3,,
200000,1,,
200000,2,,
200000,3,,
```

Average each method's three runs for each input size:

`average = (run\_1 + run\_2 + run\_3) / 3`

## Complexity Summary

|Question / approach|Time complexity|Auxiliary space|
|-|-:|-:|
|Q1 decision chain|O(k) worst case|O(1)|
|Q2 loop|O(a)|O(1)|
|Q3 string normalisation and validation|O(L)|O(L)|
|Q4 `join()`|O(L + n)|O(L), plus stored parts|
|Q5 append one item|O(1) average|O(n) for an order of n items|
|Q6 plain recursion|O(phi^n)|O(n) stack|
|Q6 memoisation|O(n)|O(n)|
|Q6 iterative solution|O(n)|O(1)|

Where:

* `k` is the number of decision categories.
* `a` is the maximum number of valid OTP attempts.
* `L` is the total string length.
* `n` is the relevant number of elements or steps.
* `phi` is the golden ratio (approximately 1.618).

## Libraries Used

All imports are from the Python standard library:

* `time` – measuring elapsed execution time with `perf\_counter()`.
* `re` – optional regular-expression validation alternative in Q3.
* `functools.lru\_cache` – memoisation in Q6.
* `io.StringIO` – alternative text-building method in Q4.

## Submission Notes

1. Replace the repository name placeholder with the actual register number.
2. Fill in the student details above.
3. Keep one folder per task and include the `.py` or `.ipynb` files.
4. Include input files and output screenshots where applicable.
5. Include raw counts and timings used in the analysis.
6. Commit progressively: at least one commit per task. Do not upload everything in a single final commit.
7. Add the repository link to the assignment report and submit it as instructed by the faculty.

## Result Note

Add a short result note after executing each task. Example:

* **Q1:** The if-elif-else design produced one decision for each household.
* **Q2:** Blank OTP entries did not consume an attempt; three wrong valid entries caused lockout.
* **Q3:** Valid formats were normalised and displayed in receipt format; invalid formats were rejected.
* **Q4:** The measured results compared repeated concatenation and `join()`.
* **Q5:** Using `None` as the default created independent customer orders.
* **Q6:** Memoisation reduced repeated calls; the iterative method avoided recursion-depth limits.
* **Q7:** The iterative redesign returned the same result with constant auxiliary space.

Update these notes if your observed results differ.

