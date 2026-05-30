# Warhammer 40k dice system

Roll 2 or more D6 dice, where the 1st die is the Wrath die.

Count successes, sixes, and note if the Wrath die is 1 or 6.


# To install

```sh
make clobber all
sudo make install clobber
```


# Example

After installing, and assuming /usr/local/bin is in your `$PATH`:

```sh
wd6 5
Successes: 4   Sixes: 1   Wrath: 3 ..   D6: 6 2 5 4

wd6 8
Successes: 5   Sixes: 0   Wrath: 5 ..   D6: 4 4 3 2 2 5 5

wd 5
Successes: 5   Sixes: 1   Wrath: 6 ++   D6: 4 4 2 2 5

wd6 4
Successes: 0   Sixes: 0   Wrath: 1 !!   D6: 2 2 2
```


# To use

```
usage: /usr/local/bin/wd6 [-h] [-v level] [-V] [-n] [-N] [-s shuf] count

    -h          print help message and exit
    -v level    set verbosity level (def level: 0)
    -V          print version string and exit

    -n          go thru the actions, but do not update any files (def: do the action)
    -N          do not process anything, just parse arguments (def: process something)

    -s shuf     path to the shuf tool (def: .. as found on your $PATH)

    count       number of dice to roll, including the mandatory wrath die
                    NOTE: must be >= 2

Exit codes:
     0         all OK
     1         invalid count, or shuf tool failure
     2         -h and help string printed or -V and version string printed
     3         command line error
     5         some internal tool is not found or not an executable file
 >= 10         internal error

wd6 version: 1.1.1 2026-05-29
```


# Reporting Security Issues

To report a security issue, please visit "[Reporting Security Issues](https://github.com/lcn2/wd6/security/policy)".
