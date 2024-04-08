# Menstrual

import datetime

def calculate_period_length(start_date, end_date):
    period_length = (end_date - start_date).days + 1
    return period_length

def track_cycle():
    cycle_length = int(input("Enter the length of your menstrual cycle in days: "))
    last_period_date = input("Enter the start date of your last period (yyyy-mm-dd): ")
    year, month, day = map(int, last_period_date.split("-"))
    start_date = datetime.date(year, month, day)
    
    # Calculate the next expected period date
    current_date = datetime.date.today()
    next_period_date = start_date + datetime.timedelta(days=cycle_length)
    
    # Print the next expected period date until it exceeds the current date
    while next_period_date <= current_date:
        print(f"Next expected period date: {next_period_date}")
        start_date = next_period_date
        next_period_date = start_date + datetime.timedelta(days=cycle_length)
    
    # Print the number of days until the next expected period date
    days_until_next_period = (next_period_date - current_date).days
    print(f"Days until the next expected period: {days_until_next_period}")

# Call the function to track the menstrual cycle
track_cycle()
