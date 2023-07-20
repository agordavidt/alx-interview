#!/usr/bin/python3
import random
import sys
from time import sleep
import datetime

# Variables to store statistics
file_sizes_by_status = {}
total_file_size = 0
lines_processed = 0

try:
    for i in range(10000):
        # Sleep for a random time to simulate input
        sleep(random.random())

        # Generate random data
        ip_address = f"{random.randint(1, 255)}.{random.randint(1, 255)}.{random.randint(1, 255)}.{random.randint(1, 255)}"
        date_time = datetime.datetime.now()
        status_code = random.choice([200, 301, 400, 401, 403, 404, 405, 500])
        file_size = random.randint(1, 1024)

        # Print the data
        sys.stdout.write(f"{ip_address} - [{date_time}] \"GET /projects/260 HTTP/1.1\" {status_code} {file_size}\n")
        sys.stdout.flush()

        # Collect statistics
        if status_code in file_sizes_by_status:
            file_sizes_by_status[status_code] += 1
        else:
            file_sizes_by_status[status_code] = 1

        total_file_size += file_size
        lines_processed += 1

        # Print statistics after every 10 lines
        if lines_processed % 10 == 0:
            print(f"\nTotal file size: {total_file_size}")
            for status_code in sorted(file_sizes_by_status.keys()):
                print(f"{status_code}: {file_sizes_by_status[status_code]}")
            print("-------------------")

except KeyboardInterrupt:
    # Handle keyboard interruption (CTRL + C)
    print("\nExiting...")

