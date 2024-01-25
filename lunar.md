**Title:** Lunar Phase Calculator

**Description:**  
Welcome to your Python programming exercise! As a beginner, you will embark on a journey to explore basic programming concepts such as loops and functions. In this exercise, you will create a simple program that calculates and displays the phases of the Moon based on a given date range. This exercise is inspired by the fascination with the Moon, a key element in space exploration and observation through telescopes.

Your task is to write a Python function named `lunar_phase_calculator` that takes two dates as input: a start date and an end date. The function will then calculate and print the lunar phase for each day in this range. For simplicity, we will use a basic approach to estimate the lunar phase:

- The lunar cycle is approximately 29.5 days.
- For simplicity, assume the lunar cycle starts on the first day of the month with a 'New Moon'.
- The phases are New Moon, Waxing Crescent, First Quarter, Waxing Gibbous, Full Moon, Waning Gibbous, Last Quarter, and Waning Crescent.

**Input-Output Example:**

```python
start_date = "2024-02-01"
end_date = "2024-02-08"
lunar_phase_calculator(start_date, end_date)
```

Output:

```
2024-02-01: New Moon
2024-02-02: Waxing Crescent
2024-02-03: Waxing Crescent
2024-02-04: First Quarter
2024-02-05: Waxing Gibbous
2024-02-06: Waxing Gibbous
2024-02-07: Waxing Gibbous
2024-02-08: Full Moon
```

**Solution:**

```python
from datetime import datetime, timedelta

def lunar_phase_calculator(start, end):
    phases = ["New Moon", "Waxing Crescent", "First Quarter", "Waxing Gibbous", 
              "Full Moon", "Waning Gibbous", "Last Quarter", "Waning Crescent"]
    start_date = datetime.strptime(start, "%Y-%m-%d")
    end_date = datetime.strptime(end, "%Y-%m-%d")
    current_date = start_date

    while current_date <= end_date:
        cycle_day = (current_date - start_date).days % 29.5
        phase_index = int(cycle_day // (29.5 / len(phases)))
        print(f"{current_date.strftime('%Y-%m-%d')}: {phases[phase_index]}")
        current_date += timedelta(days=1)

# Example usage
start_date = "2024-02-01"
end_date = "2024-02-08"
lunar_phase_calculator(start_date, end_date)
```

**Reason for Exercise Creation:**  
This exercise is designed to introduce beginners to fundamental programming concepts in Python, such as functions, loops, and working with dates. It combines these concepts with an engaging theme - the lunar phases, which are often observed through telescopes and are a significant part of astronaut training and space exploration. The exercise aims to make learning interactive and fun, especially for those interested in space and data analytics.

**Step-by-Step Explanation of the Solution:**

1. **Import Required Modules:**
   - We import `datetime` and `timedelta` from the `datetime` module, which are essential for handling dates in Python.

2. **Defining the Function:**
   - The function `lunar_phase_calculator` is defined with two parameters, `start` and `end`, representing the start and end dates.

3. **Setting Up Lunar Phases:**
   - A list named `phases` contains the different lunar phases. The lunar cycle is divided into these phases.

4. **Parsing Dates:**
   - The start and end dates are converted from strings to `datetime` objects using `strptime`.

5. **Calculating and Printing Phases:**
   - A while loop runs from the start date to the end date.
   - For each date, the lunar cycle day is calculated using the modulo operator `%` with 29.5 (the approximate length of the lunar cycle in days).
   - The phase index is determined by dividing the cycle day by the length of each phase (29.5 days divided by the number of phases).
   - The corresponding lunar phase is printed for each date.

6. **Example Usage:**
   - The function is called with a specific date range to demonstrate its functionality.
