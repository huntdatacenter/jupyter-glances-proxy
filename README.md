# jupyter-glances-proxy

**[Glances](https://glances.readthedocs.io/): An eye on your system** 

Glances is a cross-platform monitoring tool which aims to present a maximum of information in a minimum of space through a curses or Web based interface. It can adapt dynamically the displayed information depending on the terminal size.

Glances is written in Python and uses the psutil library to get information from your system.


## Build

```
python3 -m pip install hatch

hatch build

ls -la dist/*
```
