# ICARUS Verilog

## What is ICARUS Verilog?

**ICARUS Verilog** is a powerful, open-source Verilog simulation and synthesis tool. It is widely used in the hardware design community to simulate, verify, and compile Verilog code. 

---

## In short:

- Verifying RTL designs.
- Debugging and analyzing waveforms when used with tools like **GTKWave**.
- Free and open-source nature.

---

## How Does ICARUS Verilog Work?

- **Input**: The user provides Verilog design files and a corresponding testbench that describes the functionality and testing of the hardware design.
- **Processing**: ICARUS Verilog compiles the Verilog files into an executable simulation file and runs the simulation to verify the design.
- **Output**: The tool generates simulation results, including a Value Change Dump (VCD) file, which records signal changes over time for waveform analysis.

---

# Steps to Install ICARUS Verilog

Follow these steps to install **ICARUS Verilog** on a Linux distribution. 


**1. Clone the ICARUS Verilog repository**:
```bash
git clone https://github.com/steveicarus/iverilog.git
```

**2. Navigate to the repository directory**:
```bash
cd iverilog
```

**3. Build the configuration files**:
```bash
sh autoconf.sh
```

**4. If you encounter errors such as missing dependencies**, install the required packages:
```bash
sudo apt-get update
sudo apt-get install gperf autoconf
```

**5. Re-run the configuration file setup**:
```bash
sh autoconf.sh
```

**6. Configure the build process**:
```bash
./configure
```

**7. If errors occur during configuration (e.g., "no acceptable C compiler found"), install the necessary packages**
```bash
sudo apt-get install gcc g++
sudo apt-get install flex
sudo apt-get install bison
```

**8. Re-run the configuration process**:
```bash
./configure
```

**9. Compile the source code**:
```bash
make
```

**10. If the `make` command is not found**, install it:
```bash
sudo apt-get install make
```

**11. Re-run the compilation**:
```bash
make
```

**12. Move all the compiled files to the appropriate system directories**:
```bash
sudo make install
```

**13. Verify the installation**:
```bash
cd
iverilog
```

---

# Installing GTKWave

## Overview

**GTKWave** is an analysis tool used for debugging Verilog or VHDL simulation models. It visualizes the output waveforms in a user-friendly interface, making it an essential tool for verifying digital designs.

---

## How Does GTKWave Work?

- **Input**: The user provides a **VCD (Value Change Dump)** file generated from a Verilog simulation tool like ICARUS Verilog.
- **Processing**: GTKWave reads the VCD file and allows users to visualize the signal changes in a waveform format, making it easier to debug and analyze the design.
- **Output**: The tool displays a graphical waveform interface where users can inspect and analyze signal interactions over time.

---

## Installation Instructions

Follow these steps to install GTKWave on a Linux distribution:

**Navigate to the home directory**
```bash
cd
```

**Install GTKWave**
```bash
sudo apt install gtkwave
```

---

# Simulation and Viewing the Output Waveform

This section demonstrates how to simulate a Verilog design and visualize the output waveform using **GTKWave**.


## Steps to Simulate and View Output

A directory named ```icarus_codes``` is created to organize the Verilog design and testbench files and showcase a simulation example.

Navigate to the new directory
```bash
cd icarus_codes
```

A Verilog design file (Mycounter.v) and testbench file (Testbench.v) is present in this directory

Compile the Verilog design and testbench from the same directory containing the files. The iverilog command compiles Mycounter.v and Testbench.v into an executable file named Mycounter in the same directory.
```bash
iverilog -o Mycounter Mycounter.v Testbench.v
```

Run the compiled simulation. The vvp command executes the compiled file, generating a dump file (count.vcd) as specified in the testbench.
```bash
vvp Mycounter
```

View the waveform output in GTKWave. The gtkwave command opens the count.vcd file in GTKWave for waveform analysis.
```bash
gtkwave count.vcd
```
