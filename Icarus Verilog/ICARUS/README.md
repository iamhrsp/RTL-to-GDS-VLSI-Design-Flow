# ICARUS Verilog

## What is ICARUS Verilog?

**ICARUS Verilog** is a powerful, open-source Verilog simulation and synthesis tool. It is widely used in the hardware design community to simulate, verify, and compile Verilog code. 

---

## In short:

- Verifying RTL designs.
- Debugging and analyzing waveforms when used with tools like **GTKWave**.
- Free and open-source nature.

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
