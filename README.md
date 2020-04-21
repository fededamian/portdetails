# portdetails

Tool written in Bash to get typical TCP / UDP Ports Usage Descriptions. Works on Linux and Mac. 

![](resources/example.gif)

`portdetails` provides descriptions on the typical usage of TCP and UDP ports and makes them available in a terminal-compatible output, with a bunch of helpful search options. Data is retrieved from the List of TCP and UDP port numbers Wikipedia entry (https://en.wikipedia.org/wiki/List_of_TCP_and_UDP_port_numbers).

There is
a local copy of this db in the tool's repository. If you want to update it
you need to run the tool with -u flag on macOS (requires brew) or on a
Debian / Ubuntu based GNU/Linux distribution.

## Installation

- Clone this repository:

  ```bash
  git clone https://github.com/fededamian/portdetails
  ```

- Go to the tool's folder:

  ```bash
  cd portdetails
  ```

- Create a symlink for the tool:

  ```bash
  ./portdetails -l
  ```

## Usage

```
NAME
  portdetails

SYNOPSIS
  portdetails [options]

DESCRIPTION
  portdetails provides descriptions on the typical usage of TCP and UDP ports
  and makes them available in a terminal-compatible output, with a bunch of
  helpful search options. Data is retrieved from the List of TCP and
  UDP port numbers Wikipedia entry
  (https://en.wikipedia.org/wiki/List_of_TCP_and_UDP_port_numbers). There is
  a local copy of this db in the tool's repository. If you want to update it
  you need to run the tool with -u flag on macOS (requires brew) or on a
  Debian / Ubuntu based GNU/Linux distribution.

OPTIONS
  -h | --help            Print this help.
  -p <port>              Search for a specific comma separated list of ports.
  -a <number>            Search for a comma separated list of numbers inside
                         ports (approximate, e.g. 80 matches 8008, 8080, etc)
  -d <search string>     Search for a comma separated list of strings
                         (case insensitive).
  -n                     Only print description(s).
  -u                     Update DB from Wikipedia.
  -l                     Create tool's symlink.

EXAMPLES
  - Get a full list of ports and the description of their typical usage.
    portdetails

  - Search for specific port 80.
    portdetails -p 80

  - Search for specific ports 139,445,3389.
    portdetails -p 139,445,3389

  - Search for specific port 80 but only print description.
    portdetails -p 80 -n

  - Search for ports that include 80 inside them (e.g. 80, 8080, 8008).
    portdetails -a 80

  - Search for ports where their description has MySQL or Postgre on them.
    portdetails -d "MySQL,Postgre"

  - Search from stdin for exact port numbers or strings separated by newlines.
    cat tests/ports.txt | portdetails
```
