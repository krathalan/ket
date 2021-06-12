# ket

**K**rathalan's **e**xposure **t**racker, or ket, is a program for radiologic technologist students to keep track of your repeat rates.

```
Usage: ket [COMMAND] (args...)

Commands:
new, e.g. "ket new"
    Create a new entry, entering the details of the exam
    you just completed.

delete-last, e.g. "ket delete-last"
    Delete the last entry you just added, in case you
    realize you put it in wrong.

today, e.g. "ket today"
    Print out all the exams you have completed today.

all, e.g. "ket all"
    Print out all exams you've ever done. Might take a while.

analyze, e.g. "ket analyze exam"
    Analyze your repeat rates by various factors. You can
    optionally provide an argument after analyze, such as
    age, basic, day-of-week, equipment, exam, patient-type,
    repeat-reasons, shift, tech, or week, to show analysis
    only for that factor.

list ARG, e.g. "ket list age --verbose"
    List some most common factors for repeats for that sub-
    category. Requires an argument, either age or exam. You
    can optionally provide -v or --verbose to additionally print
    all exams completed for that subcategory.

help, e.g. "ket help"
    Print this help
```

## Installation
Install `ket-git` from the AUR: https://aur.archlinux.org/packages/ket-git/

## Limitations
Ket wasn't designed to keep track of my repeats for over a year, so you might run into some weird issues with the today and all commands, as well as time-based analyze commands. One way to fix this is to rename your old ket data file (located at `~/.local/share/ket`) every year, to something like `data2021.json.br` when the new year rolls around, or simply delete it.

Some things are hard coded, such as the list of technologists, the shifts, and equipment, which correspond to those at my clinical site. I may add a config file in the future to fix this.