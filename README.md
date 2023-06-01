# jupyter-glances-proxy

[![PyPI - Python Version](https://img.shields.io/pypi/pyversions/jupyter-glances-proxy.svg)](https://pypi.org/project/jupyter-glances-proxy/)

**jupyter-glances-proxy** provides Jupyter extension to run Glances.

**[Glances](https://glances.readthedocs.io/): An eye on your system** 

Glances is a cross-platform monitoring tool which aims to present a maximum of information in a minimum of space through a curses or Web based interface. It can adapt dynamically the displayed information depending on the terminal size.

Glances is written in Python and uses the psutil library to get information from your system.

## Installation

You can install jupyter-glances-proxy inside your environment with Jupyter / Jupyterlab:

```
python3 -m pip install jupyter-glances-proxy
```

Glances is installed automatically as a dependency of this project.

## Build

```
python3 -m pip install hatch

hatch build

ls -la dist/*
```
