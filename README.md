# Advanced SOLVE for the HP-41 calculator

[![HP-41](https://img.shields.io/badge/HP--41-Calculator-orange)](https://en.wikipedia.org/wiki/HP-41C)
[![License](https://img.shields.io/badge/License-Public%20Domain-brightgreen.svg)](https://unlicense.org/)
[![GitHub stars](https://img.shields.io/github/stars/isene/hp-41_solve.svg)](https://github.com/isene/hp-41_solve/stargazers)
[![Stay Amazing](https://img.shields.io/badge/Stay-Amazing-blue.svg)](https://isene.org)

The HP-41 now has a SOLVE function similar to that of the HP-42S. This is an adaptation of the [SOLVE Function](https://www.hpmuseum.org/software/41solvr.htm) by Stefan Vorkoetter featuring a full Alpha menu and more. The programs included requires an HP-41CX (or HP-41CL or the DM-41X).

## SOLVE
Upon `XEQ "SOLVE"`, you will be asked to enter the function that you want to solve for a variable. The function must be written into a separate program in the format "f(x) = 0". For instance, to solve the function of [Little's Law](https://github.com/isene/hp-41_LittlesLaw), the function "T=I*R" must be written as "I*R-T" in this way:

```
001*LBL "LL"
002 "T I R"
003 FS?C 00
004 RTN
005 RCL 02
006 RCL 03
007 *
008 RCL 01
009 -
010 END 

```
The first four program lines must be in this format for any function that you want to solve. The first line is the name of the function. The second line is the menu showing the variables. The first variable is stored in register 01 and is accessed by pressing the label `A` - for entering the value for that variable or for solving for that variable. The second variable is stored in register 02 and is accessible by pressing `B`, etc. You can use up to 5 variables. Line 003 and 004 must be included for any function that you create. Lines 005 and onward is the function written in the format `f(x)=0`.

When you have entered the function that you want to operate on, SOLVE will present the menu for that function. In the example above, this will be "T I R". You can then enter values for any variable and pressing the corresponding label (`A` for the first variable, `B` for the second variable, etc.). When you have entered all but one of the variables, you can solve for the last variable by simply pressing the corresponding label key. If you enter a value and press a label key, you will set the variable to that value. If you press a label key without entering a value, the program will solve for that value. Keep entering values as you wish and solve for any variable along the way.

There are two underlying values stored in registers 11 and 12. These are the two "guess" values used for solving. By pressing `R/S` when you see the function menu, SOLVE will show the first guess value. Another `R/S` will present the second guess value. These are set to `0` and `5` by default. If you press `R/S` again, SOLVE will indicate that You can change these values by entering the first guess value, `ENTER`, the second guess value, and then press `a`.

After you enter or solve for any value, the program will show the value of that variable.

## SOLVE with XM
I included a more advanced SOLVE for the HP-41CX where the last fuction is stored in an Extended Memory data file called `SOLVE`. When you are asked to input the function to solve, the last function will be suggested. Simply press `R/S` to solve for that function. Enter any other function, and that that function will be saved to the data file and suggested the next time you run SOLVE.

## Barcode for SOLVE
Courtesy of [Josef](https://www.hpmuseum.org/forum/user-13142.html) over at the [HP Forum](https://www.hpmuseum.org/forum/), I have included the file `solve.pdf` in this repo, providing barcodes for the program that can be scanned with an HP Wand.

## License
This software is released into the Public Domain.

