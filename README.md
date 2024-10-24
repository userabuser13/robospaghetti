
# Yearly Robots Prediction

## Overview

This Python script determines whether robots could defeat humanity in a specified year based on certain criteria and checks if that year is a leap year. It takes user input for a year and evaluates two main conditions:
- The binary representation of the input year includes the binary representation of the number 42.
- The leap year status of the input year.

The script provides output that varies based on whether the year is in the past, present, or future.

## Features

- **Binary Check**: Verifies if the binary representation of the input year contains the binary representation of the number 42.
- **Leap Year Calculation**: Determines if the input year is a leap year based on standard rules.
- **Dynamic Responses**: Outputs responses that reflect past, present, and future contexts regarding the possibility of robots defeating humanity.

## Requirements

- Python 3.x

## How to Run

1. Clone this repository to your local machine using:
   ```bash
   git clone https://github.com/yourusername/Yearly-Robots-Prediction.git
   ```
2. Navigate into the project directory:
   ```bash
   cd Yearly-Robots-Prediction
   ```
3. Run the script using Python:
   ```bash
   python your_script_name.py
   ```
4. Enter a year when prompted.

## Code Example

Here's the formatted main code for the script:

```python
from datetime import datetime

current_year = datetime.now().year

n = int(input('Enter year: '))
leap_year = n % 4 == 0 and n % 100 != 0 or n % 400 == 0
bin_n = bin(n)[2:]
bin_42 = bin(42)[2:]

if n < current_year:
    robots = f"Yes, robots could defeat humanity in {n}, " if bin_42 in bin_n else f"No, robots couldn't defeat humanity in {n}, "
    leap_text = "and it was a leap year" if leap_year else "and it wasn't a leap year"
elif n == current_year:
    robots = f"Yes, robots can defeat humanity in {n}, " if bin_42 in bin_n else f"No, robots can't defeat humanity in {n}, "
    leap_text = "and it's a leap year" if leap_year else "and it's not a leap year"
else:
    robots = f"Yes, robots can defeat humanity in {n}, " if bin_42 in bin_n else f"No, robots can't defeat humanity in {n}, "
    leap_text = "and it will be a leap year" if leap_year else "and it won't be a leap year"

print(robots + leap_text)
```

## Example

Input:
```
Enter year: 2024
```

Output:
```
No, robots can't defeat humanity in 2024, and it's a leap year
```
