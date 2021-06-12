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

# Examples

```
 $ ket analyze age
----------------------
|   By age bracket   |
----------------------
1-10 rate: 0% (8E/0R)
11-20 rate: 7.58% (66E/5R)
21-30 rate: 1.75% (57E/1R)
31-40 rate: 3.64% (55E/2R)
41-50 rate: 2.54% (118E/3R)
51-60 rate: 4.44% (90E/4R)
61-70 rate: 6.43% (140E/9R)
71-80 rate: 5.84% (137E/8R)
81-90 rate: 6.67% (75E/5R)
91-100 rate: 0% (39E/0R)
101-110 rate: 0% (6E/0R)

 $ ket analyze exam
--------------------
|   By exam type   |
--------------------
chest rate: 4.66% (193E/9R)
ribs rate: 11.76% (34E/4R)
finger rate: 0% (30E/0R)
hand rate: 0% (27E/0R)
wrist rate: 0% (48E/0R)
forearm rate: 0% (6E/0R)
elbow rate: 10% (20E/2R)
humerus rate: 0% (2E/0R)
shoulder rate: 6.25% (48E/3R)
clavicle rate: 0% (2E/0R)
toe rate: 14.29% (7E/1R)
foot rate: 5% (20E/1R)
ankle rate: 5.71% (35E/2R)
knee rate: 6.06% (99E/6R)
tib-fib rate: 5.88% (17E/1R)
femur rate: 3.57% (28E/1R)
cspine rate: 0% (19E/0R)
tspine rate: 4.55% (22E/1R)
lspine rate: 3.03% (33E/1R)
pelvis rate: 10% (10E/1R)
hip rate: 6.90% (29E/2R)
sacrum-coccyx rate: 14.29% (7E/1R)
scoliosis rate: 33.33% (3E/1R)
abdomen rate: 0% (18E/0R)
abdomen-upright rate: 0% (19E/0R)

 $ ket list exam
------------------------
|   Exam type: chest   |
------------------------
chest rate: 4.66% (193E/9R)

Most repeats on different equipment:
4 2
3 n
2 o

Most repeated views:
7 ap
1 pa
1 lateral

Most repeat reasons:
3 centering-low
3 artifact
1 rotation
1 centering-high
1 anatomy-cutoff

-----------------------
|   Exam type: ribs   |
-----------------------
ribs rate: 11.76% (34E/4R)

Most repeats on different equipment:
3 2
1 1

Most repeated views:
3 oblique
1 ap

Most repeat reasons:
1 marker-in-anatomy
1 centering-right
1 centering-high
1 centering
...
-----------------------
|   Exam type: knee   |
-----------------------
knee rate: 6.06% (99E/6R)

Most repeats on different equipment:
4 2
1 1

Most repeated views:
3 lateral
2 ap
1 lat

Most repeat reasons:
2 rotation
2 overrotation
1 other
1 anatomy-cutoff
...
```

## Installation
### Arch
Install `ket-git` from the AUR: https://aur.archlinux.org/packages/ket-git/

### Other distros
Clone this repo and add it to your `$PATH`. Please submit an issue if you make a package for another distro!

## Limitations
Ket wasn't designed to keep track of my repeats for over a year, so you might run into some weird issues with the today and all commands, as well as time-based analyze commands. One way to fix this is to rename your old ket data file (located at `~/.local/share/ket`) every year, to something like `data2021.json.br` when the new year rolls around, or simply delete it.

Some things are hard coded, such as the list of technologists, the shifts, and equipment, which correspond to those at my clinical site. I may add a config file in the future to fix this.