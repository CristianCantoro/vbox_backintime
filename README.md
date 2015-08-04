# VBox Time Machine

VBox Time Machine is a simple script to change the system time of your
VirtualBox virtual machines.

## Usage
```
Usage: vbox_backintime [options] [<name>]

      --date DATE        Use DATE as base date, format %Y-%m-%d as in date 
                         command (default: 2015-06-20)
      --now              Set the date to the current host system time
                         (i.e. now, the result of the date command).
      --list             List names of available virtual machines and exits.
      -v, --verbose      Generate verbose output.
      -h, --help         Show this help message and exits.
      --version          Print version and copyright information.
```

**You need to run the script _before_ starting the VM.**

The script will always print the command used, i.e.:
```
vboxmanage modifyvm $vm_name  --biossystemtimeoffset $offset
```

If you do not specify a machine name you will be show a list and asked for a
choice, like in the example below:
```
$ ./vbox_timemachine
Available virtual machines:
0: "myvm1"
1: "Another VM"
2: "vagrant_default_1436359701720_3067"
-> Select the VM no.:

```

Running with `--verbose` will print some additional info:
```
$ ./vbox_timemachine --verbose myvm1
Will modify the virtual machine named: myvm1

Current system time is: mer  5 ago 2015, 00.09.09, CEST
Current system time is (milliseconds from epoch): 1438726149946

Offset in milliseconds is: -3938020946
Base date is (milliseconds from epoch): 1434788129000
Base date is: 20-06-2015 10:15:29 +0200

vboxmanage modifyvm "myvm1" --biossystemtimeoffset -3938020946
```

## Prerequisites

To run this script you need [`docopts`](https://github.com/docopt/docopts) 
(and also `vboxmanage` that should come with your `VirtualBox` installation)
(yeah, you also need VirtalBox, you didn't say?).