# Frequency Distribution Analysis

A C/C++ command-line program for analyzing byte frequency distributions in files, created as part of **EECS 4/5760 – Computer Security – Fall 2024**.

This tool generates histograms and summary statistics for plaintext and encrypted files, helping visualize how encryption flattens character distributions.

---

## Features

Analyze byte frequencies across all 256 possible byte values (0–255).  
Display scaled vertical histograms in the terminal.  
Support ASCII or numeric X-axis labels.  
Logarithmic scaling option for better visualization.  
Adjustable histogram height.  
Option to suppress the graph and show summary statistics only.  
Compute minimum, maximum, average, and standard deviation of byte frequencies.  
(Graduate Option) Analyze digrams, trigrams, and octagrams for deeper cryptographic insights.

---

## Command-Line Usage


### Options

- `-a`  
  Show printable ASCII characters along the X-axis.

- `-n`  
  Show byte values (0–255) along the X-axis in three rows.

- `-r<nn>`  
  Set histogram height to `nn` rows (default: 20).  
  *Example*: `-r50`

- `-l`  
  Use logarithmic scaling on the Y-axis.

- `-g`  
  Suppress the graph; output summary statistics only.
  
**Example Command:**
FrequencyDistribution.exe -a -r50 -l Shakespeare.TXT

Options can appear in any order.

---

## Output

The program prints:
- A **256-column histogram** of byte frequencies.
- A summary line showing: Min:XXXXXXXXX Max (CCC):XXXXXXXXX AVG:XXXXXXXXX DEV:XXXXXXXXX
- `CCC` is the most frequent byte value (000–255).
- Values are scaled to 9-character fields.

When both `-n` and `-a` are specified, numeric labels appear first, followed by ASCII labels.

---

## Example
![](https://github.com/SakshiD16/Frequency-Analysis-in-Cryptography/blob/main/docs/Screenshot%202025-06-28%20133734.png)
![](https://github.com/SakshiD16/Frequency-Analysis-in-Cryptography/blob/main/docs/Screenshot%202025-06-28%20133710.png)
![](https://github.com/SakshiD16/Frequency-Analysis-in-Cryptography/blob/main/final.png)
---

## Building the Project

This project is developed in **Visual Studio 2022**.  
You must:

1. Use Visual Studio 2022 (Community Edition acceptable).
2. Build **x64 Release configuration**.
3. Avoid any C++ template library (e.g., vectors, maps).
4. Use only arrays and your own data structures.

To build:

1. Open the `.sln` solution file in Visual Studio.
2. Select `Release` and `x64`.
3. Build the solution (`Build > Build Solution`).

---

## Testing

You are encouraged to test your program on:
- The provided `Shakespeare.TXT`, `Shakespeare.ECB`, and `Shakespeare.CBC` files.
- Smaller sample files you create yourself.

**Important:**
- The sum of all byte counts must exactly match the file size.
- For graduate credit, include digram/trigram/octagram statistics.

---

## Notes

- The program must accept the filename as a **single command-line argument** and **must not prompt** the user for input.
- For files >4GB or with high frequency counts, the program must still function correctly.
- Ensure your terminal is set wide enough (≥259 characters) for correct display.

---

## License

This project is provided as coursework for EECS 4/5760.  
**Do not distribute or reuse this code outside the course context.**


