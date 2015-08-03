# VBox Time Machine

VBox Time Machine is a simple script to change the system time of your
VirtualBox virtual machines.

## Usage
```
Usage: vbox_backintime [options] [<name>]

      --date DATE        Use DATE as base date, format %Y-%m-%d as in date 
                         command (default: 2015-06-20)
      --list             List names of available virtual machines
      --verbose          Generate verbose messages.
      --help             Show help options.
      --version          Print program version.
```

You need to run the script _before_ starting the VM.
s
## Prerequisites

To run this script you need [`docopts`](https://github.com/docopt/docopts).