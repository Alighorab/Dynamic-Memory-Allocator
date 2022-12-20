# Simple Allocator

## Description

- A dynamic memory allocator for C programs, i.e., my own version of `malloc`,
  `free`, and `realloc` routines.
- The 6th lab of [15-213: Introduction to Computer Systems.](https://www.cs.cmu.edu/afs/cs.cmu.edu/academic/class/15213-f15/www/schedule.html)
- I use implicit list to keep track of free blocks.
- Placement policy: first fit or next fit (if you define `NEXT_FIT` macro)
- Splitting policy: splitting only if the size of remainder would equal or
  exceed the minimum block size.
- This is a special-purpose allocator not like `libc` `malloc` package which is
  general-purpose.

## How to test it?
- Open your terminal and run the following:
    - `git clone https://github.com/Alighorab/Simple-Allocator.git`
    - `cd Simple-Allocator`
    - `make`
    - `./mdriver -h` to get help.

## Lab Files
- `mm.{c,h}`: The `malloc` package implementation.
- `mdriver.c`: The `malloc` driver that tests `mm.c` file.
- `short{1,2}-bal.reb`: Two tiny tracefiles to help you get started.
- `Makefile`: Builds the project.
- Other `files` are support files for the driver.

## My Score
```
Results for mm malloc:
trace  valid  util     ops      secs  Kops
 0       yes   91%    5694  0.001878  3033
 1       yes   92%    5848  0.001057  5534
 2       yes   95%    6648  0.003100  2145
 3       yes   97%    5380  0.003309  1626
 4       yes   66%   14400  0.000116124460
 5       yes   91%    4800  0.003801  1263
 6       yes   89%    4800  0.003460  1387
 7       yes   55%   12000  0.014830   809
 8       yes   51%   24000  0.007655  3135
 9       yes   27%   14401  0.114320   126
10       yes   45%   14401  0.002354  6118
Total          73%  112372  0.155878   721

Perf index = 44 (util) + 40 (thru) = 84/100
```
