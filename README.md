# [EFC] Epitech Banned Function Checker

![Screenshot of the program running and detecting a banned function inside a binary.](./docs/preview.png "Sreenshot of the program running")

> **Warning**: The program will only run on UNIX systems.

> ***Note**: The program is only tested on NixOS.*

## Dependencies

### On Nix systems

Nothing ! Everything is provided by the [flake.nix](./flake.nix) file.

### On other systems

- [GNU binutils](https://www.gnu.org/software/binutils/)
- [Python 3](https://www.python.org/)

## Usage

If you don't specify the path to the authorized functions,
the program will use the default one: `./bonus/authorized_functions.txt`

### On Nix systems

```bash
nix run github:Dawoox/efc </path/to/your/binary> [/path/to/authorized_functions.txt]
```

### On other systems

```bash
python3 ./EpiFunctionChecker/main.py </path/to/your/binary> [/path/to/authorized_functions.txt]
```

## authorized_functions.txt

The file must contain the list of authorized functions, one per line. <br>
For example (from the setting_up project):

```txt
open
read
write
close
malloc
free
stat
```

## Limitations

- On some projects, the TA authorizes some functions without it being writing on the subject. On the setting_up project for example, the TA authorizes the use of `memset` without it being written on the subject.
- We can't provide a trace back to the line where the banned function is used. We can only provide the name of the function (and the address where it is used, but it won't show up in the output).
