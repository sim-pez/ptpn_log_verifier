![GitHub last commit](https://img.shields.io/github/last-commit/sim-pez/ptpn_log_verifier)


# Introduction
This program reads a preemptive time petri net (PTPN) and verifies the feasibility of a real time program execution log. This work is based on [Sirio Library](https://github.com/oris-tool/sirio) and is an extension of @[loremacchia](https://github.com/loremacchia)'s work.

## Algorithm
Here is the pseudo-algorithm to check the log feasibility:

1. Read next transition *t* and time to fire *tau* from log
2. Check if *t* is an *enabled transition*
3. Check if *t* is a *progressing transition*
4. Check if *tau* is in the [min<sub>t</sub> , max<sub>t</sub>] interval provided from PTPN
5. Check if *tau* is <= max<sub>t'</sub> for each progressing transition t'
6. If all above checks are ok, update the time to fire of enabled transitions and go to 1

# PTPN
You need to create a PTPN model of your real time program. We reccomend to use [Oris tool](https://www.oris-tool.org/) in order to create Java code from a graphic model

# log format
The log file must be a `.txt` file in this format:
```
[transition name]
[time to fire]
[transition name]
[time to fire]
...
```
Example:
```
t0
900
t1
30
t5
260
...
```
Noteてゃｔ, you need to provide the same transition name of PTPN transitions


# Acknowledgments
Software Engineering for Embedded Systems - Computer Engineering Master Degree @[University of Florence](https://www.unifi.it/changelang-eng.html).
