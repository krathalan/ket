# ket

**K**rathalan's **e**xposure **t**racker, or ket, is a program for radiologic technologist students to keep track of your repeat rates.

Run `ket new` to make a new entry. Ket will ask you a series of questions with a list of viable answers, and then save it as an exposure entry. Data is stored at `~/.local/share/ket` as compressed json.

Run `ket today` to show a summary of all the exams you have completed "today".

Run `ket delete-last` to delete the last entry. Use this in case of input error after you have completed an aberrant entry, or press Ctrl+C to cancel the input process

Run `ket analyze` (optionally with an argument) to get repeat rates. As of now, ket will analyze your repeat rates by:
- age bracket
- overall/basic stats
- day of week
- equipment used
- exam type (e.g. chest, pelvis)
- patient type (e.g. in vs outpatient)
- shift (morning/evening/weekend)
- registered tech you worked with
