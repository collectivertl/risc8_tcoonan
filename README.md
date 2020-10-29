# RISC8 Core

[![Build Status](https://dev.azure.com/collectivertl/Test/_apis/build/status/collectivertl.risc8_tcoonan?branchName=main)](https://dev.azure.com/collectivertl/Test/_build/latest?definitionId=3&branchName=main)
[![Documentation Status](https://readthedocs.org/projects/risc8-tcoonan/badge/?version=latest)](https://risc8-tcoonan.readthedocs.io/en/latest/?badge=latest)

By: Tom Coonan

risc8_tcoonan is a Verilog implementation of a simple 8-bit processor. The RISC8 is binary code compatible with the Microchip 16C57 processor.

---

## Project Layout 

### doc

Design documentation

```
make
```

Command will build HTML and PDF.  The HTML is what is displayed on 'Read the Docs'.

### dv

Design verification files

```
make
```

Command will generate the required files for simulation from the provided files, then it will run the simulation.

### rtl

Design files used for synthesis

## Contributing

The design development and verification can be performed via a docker container from VsCode.  To do this:

- Install VsCode
- Install Docker
- Install VsCode Extensions
  - Remote Development
  - Remote - Containers
  - Docker
  - Verilog-HDL/SystemVerilog
  - reStructuredText
- Clone the repository to your machine
- In VsCode
  - File -> Open Folder
  - Select the repository folder
  - After it is open VsCode will prompt to open in container, do that
  - The container will build
  - Once complete you should have a Terminal / bash prompt available in the folder to perform development

I've only done this with Windows 10 Pro which allows for a regular Docker installation.  I would expect this can run on Linux as well but haven't tested it yet.