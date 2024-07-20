# Doctor's appointment management system using Object Oriented Programming in C++.

## Overview

This project implements a doctor appointment booking system using C++. The system allows users to book appointments, mark them as done, view bookings for a specific day, and review the history of completed appointments.

## Components

### 1. `datetype` Class

The `datetype` class represents a date in the format `dd/mm/yy`. It includes:
- **Data Members**: `d` (day), `m` (month), `y` (year)
- **Operator Overloading**: For input/output streaming and comparison

### 2. `Patient` Class

The `Patient` class represents a patient with:
- **Data Members**: `name` and `contact`

### 3. `Timeslot` Class

The `Timeslot` class manages individual time slots:
- **Data Members**: `booked` (indicates if slot is booked), `p` (pointer to `Patient`), `done` (indicates if appointment is completed)
- **Methods**:
  - `addPatient()`: Adds a patient to the slot
  - `deletePatient()`: Removes a patient from the slot
  - `showDetails()`: Displays the details of the time slot

### 4. `Date` Class

The `Date` class manages a collection of `Timeslot` objects for a specific date:
- **Data Members**: `date1` (instance of `datetype`), `t` (array of `Timeslot`)
- **Methods**:
  - `slot_init()`: Initializes time slots
  - `freets(int i)`: Checks if a given time slot is free

### 5. Global Functions

- **`checkdate(list<Date *> &dl, datetype da)`**: Checks if a `Date` object exists in the list and returns a pointer to it.
- **`findDate(datetype da)`**: Finds or creates a `Date` object for the given date.
- **`fileAppend(Date *da, int i, string fileName)`**: Appends booking information to a file.
- **`booking()`**: Allows a user to book an appointment.
- **`markDone()`**: Marks an appointment as done.
- **`daybookings()`**: Displays all bookings for a specific day.
- **`history(int n)`**: Shows the last `n` completed bookings.
- **`display()`**: Placeholder for additional display modes.
- **`populate()`**: Reads existing bookings from a file and populates the data.

## Files

- `bookings.csv`: Stores booking details.
- `done.csv`: Stores completed appointments.
- `intro.txt`: Contains the introductory menu and options.

## How to Run

1. **Compile the Code**

   Use a C++ compiler to compile the code. For example, with g++:

   ```bash
   g++ -o appointment_system appt1.cpp
   ```

2. **Run the Executable**

    Execute the compiled program:
    ```bash
    ./appointment_system
    ```

## Class Diagram
[![](https://mermaid.ink/img/pako:eNqNVU1r3DAQ_StCh-DdOiEpzcU4hsLSUwuFtqd1KKo13hVrS0aSG0zY_96R1na0_ijxSTPzZvRm5tl-pYXiQBNaVMyYnWAHzepcEny8h3BmwXYNkNeL1z0fhLSET-x6YneBrYzVwOobohrQzCqdptHgi0mhpLHjRTebILFcSCzfkyimiVkWiTHxfXdhSvn_lD9KVSP86SmaEFpjeM5lOOLvzArAiYUTLo5ME8lq2H-6f576saplhd1_vAr1ZXoSDrgdCHhj-fKfogZTKTvbL_Z2Aj6vvyXNVAlKQuD6qwQnjPOBz2Ya41CBhdWwOaqXHVgmKhMtc97hPK_4jiJ1h4cgMHZn94_Ps4sw8FtIcc3BdVRqAGsidxTrFL6ioEIaaVqhJ8uCYg62xfFDcXLUIgdIvTMLNLWZZZRCcneKJpAJiy-igl8WB3U1Dd9ciaHPTQOSR75kTLCbmKCehTzMZt6opq3cfbPIERkr3blZLHP4xoSciadG57yWkxTePg_UTJ92qKIFrbCuzzILQWGainUzlYxyyOlDTsntbdafhjctIa0BcwGPElkHqxfZg73yQuAjnsYKyeXNFCHaiyTMuL-726LhKyXYuWSHgcrbOtcTcLr4uSlsn-KnP2X-VidsdBE6UhyQNKY1aNwfx5-CX2tO7RFqyGmCR46bymkuz4hjrVU_OlnQxOoWYqpVezjSpGSVQatt3Br6P0rvPf8Dz7nuXQ?type=png)](https://mermaid.live/edit#pako:eNqNVU1r3DAQ_StCh-DdOiEpzcU4hsLSUwuFtqd1KKo13hVrS0aSG0zY_96R1na0_ijxSTPzZvRm5tl-pYXiQBNaVMyYnWAHzepcEny8h3BmwXYNkNeL1z0fhLSET-x6YneBrYzVwOobohrQzCqdptHgi0mhpLHjRTebILFcSCzfkyimiVkWiTHxfXdhSvn_lD9KVSP86SmaEFpjeM5lOOLvzArAiYUTLo5ME8lq2H-6f576saplhd1_vAr1ZXoSDrgdCHhj-fKfogZTKTvbL_Z2Aj6vvyXNVAlKQuD6qwQnjPOBz2Ya41CBhdWwOaqXHVgmKhMtc97hPK_4jiJ1h4cgMHZn94_Ps4sw8FtIcc3BdVRqAGsidxTrFL6ioEIaaVqhJ8uCYg62xfFDcXLUIgdIvTMLNLWZZZRCcneKJpAJiy-igl8WB3U1Dd9ciaHPTQOSR75kTLCbmKCehTzMZt6opq3cfbPIERkr3blZLHP4xoSciadG57yWkxTePg_UTJ92qKIFrbCuzzILQWGainUzlYxyyOlDTsntbdafhjctIa0BcwGPElkHqxfZg73yQuAjnsYKyeXNFCHaiyTMuL-726LhKyXYuWSHgcrbOtcTcLr4uSlsn-KnP2X-VidsdBE6UhyQNKY1aNwfx5-CX2tO7RFqyGmCR46bymkuz4hjrVU_OlnQxOoWYqpVezjSpGSVQatt3Br6P0rvPf8Dz7nuXQ)