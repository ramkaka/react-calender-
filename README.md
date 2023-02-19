# react-calender-
I assume you want a complete code for a rectangular calendar without using any external libraries. Here's an example code that can create a rectangular calendar:
def print_calendar(year, month):
    # Get the number of days in the month
    if month == 2:
        if year % 4 == 0 and (year % 100 != 0 or year % 400 == 0):
            days_in_month = 29
        else:
            days_in_month = 28
    elif month in [4, 6, 9, 11]:
        days_in_month = 30
    else:
        days_in_month = 31

    # Determine the day of the week the first day of the month falls on
    first_day = datetime.date(year, month, 1).weekday()

    # Create a list of tuples representing each day in the month
    days = [(day + 1, (first_day + day) % 7) for day in range(days_in_month)]

    # Print the calendar
    print("{0} {1}".format(datetime.date(year, month, 1).strftime("%B"), year))
    print("Mo Tu We Th Fr Sa Su")

    for day, weekday in days:
        if weekday == 0 and day != 1:
            print()
        print("{0:2}".format(day), end=" ")
    print()

# Example usage:
print_calendar(2023, 2)

