# Ticket Booking System

A simple command-line ticket booking application built in Python. It lets users check a PNR status or reserve tickets for one or more passengers, entering each passenger's name, age, and sex.

## Features

- **Check PNR Status** — Displays a sample PNR status.
- **Ticket Reservation** — Lets you enter details (name, age, sex) for any number of passengers, with an option to keep adding more before finalizing.
- **Ticket Summary** — Once reservation is complete, prints a summary listing every booked ticket.

## Requirements

- Python 3.x (no external dependencies)

## How to Run

```bash
python bussu.py
```

## Usage

1. Run the script.
2. Choose an option:
   - `1` — Check PNR status
   - `2` — Reserve tickets
3. If reserving tickets:
   - Enter the number of tickets you want.
   - Enter the name, age, and sex for each passenger.
   - When asked *"Did you forgot someone?"*, answer `y` to add more passengers or `n` to finish and view the ticket summary.

## Example

```
Ticket Booking System

1.Check PNR status
2.Ticket Reservation

Enter your option : 2

Enter no. of Ticket you want : 1

Name : John Doe
Age  : 29
Male or Female : Male

Did you forgot someone? y/n: n

Total Ticket :  1
Ticket :  1
Name :  John Doe
Age  :  29
Sex :  Male
```

## Known Limitations

- The PNR status check always returns a fixed placeholder value (`t3`) rather than looking up a real record, and exits the program immediately after.
- No input validation — entering non-numeric values for age or the menu option will raise an error.
- The `restart` loop condition (`restart != ('N','NO','n','no')`) compares a string to a tuple, which is always `True`; the loop actually exits via `exit(0)` (PNR option) or by falling through after the ticket summary is printed, not through this condition.
- Ticket data is not saved between runs — everything is stored in memory only.

## Possible Improvements

- Add real input validation (e.g., `try/except` around numeric inputs).
- Fix the `restart` loop condition to properly check membership in a list/tuple (e.g., `restart not in ('N','NO','n','no')`).
- Persist bookings to a file or database.
- Implement an actual PNR lookup system.
- Add ticket pricing, seat selection, or class options.

## License

Add a license of your choice (e.g., MIT) if you plan to share this publicly.
