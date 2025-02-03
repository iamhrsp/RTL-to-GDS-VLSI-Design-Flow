# COVERED Verilog Code Coverage Analyzer

## What is COVERED?

**COVERED** is an open-source tool designed to analyze **code coverage** in Verilog designs. It helps estimate how much of the RTL design has been exercised by a given testbench, providing insights into the completeness and quality of testing.

---

## In short:

-  Measures testbench effectiveness in covering RTL design.
-  Works with Verilog designs and Value Change Dump (VCD) files.
-  Produces detailed coverage reports displayed in the terminal.
-  Open-Source and freely available.

---

## How Does COVERED Work?

1. **Input**: Verilog design files, a testbench, and a **VCD file** generated during simulation.
2. **Processing**: The tool analyzes the provided files to compute the coverage percentage and identify untested areas.
3. **Output**: A detailed coverage report indicating the effectiveness of the testbench.


---

# Steps to Install COVERED Verilog Code Coverage Analyzer

This guide provides step-by-step instructions for installing **COVERED** :


1. Clone the GitHub repository
   ```bash
   git clone https://github.com/chiphackers/covered
   ```

2. Change directory to 'covered'
   ```bash
   cd covered
   ```

3. Configure the installation
   ```bash
   ./configure
   ```

4. Compile the source code
   ```bash
   make
   ```

5. If you encounter the error: "Tcl_Interp has no member named 'result'", follow the steps below:
   
      a. Navigate to the source code directory  
         **cd covered  
         cd src**

      b. Open the report.c file for editing  
         **gedit report.c**

      c. Locate the list of #include commands in the report.c file  
         Find the line:  
         **#include <tcl.h>**

      d. Add the following line before #include <tcl.h>:  
         **#define USE_INTERP_RESULT 1**

      e. Your updated file should look like this:  
         **#ifdef HAVE_TCLTK  
         #define USE_INTERP_RESULT 1  
         #include <tcl.h>**

      f. Save the report.c file

      g. Re-run the make command  
         **make**

6. Install the required dependencies if they are not already installed
   ```bash
   sudo apt-get update
   sudo apt-get install zlib1g-dev
   git clone https://git.savannah.gnu.org/git/libiconv.git
   sudo apt-get install tcl8.6
   sudo apt-get install tcl8.6-dev
   sudo apt-get install tk8.6
   sudo apt-get install tk8.6-dev
   sudo apt-get install doxygen
   ```

7. Reconfigure the installation
   ```bash
   ./configure
   ```

8. Compile the source code again
   ```bash
   make
   ```

9. Install the application files to the appropriate system directories
   ```bash
   sudo make install
   ```

# Generate the Code Coverage Report

To estimate the percentage of RTL design tested by the testbench, the **COVERED Verilog Code Coverage Analyzer** tool is used.

a. Generate the code coverage report in the same directory (icarus_codes) by executing the following command in the directory containing the other files:
```bash
   covered score -t Testbench -v Testbench.v -v Mycounter.v -vcd count.vcd -o Mycounter.cdd
```

b. To view the coverage report, execute:
```bash
   covered report -d v Mycounter.cdd
```
This is how the terminal displays the coverage report. Notice how the tool has various section, for example combinational section, toggle section etc.
![report](https://github.com/iamhrsp/RTL-to-GDS-VLSI-Design-Flow/blob/main/Icarus%20Verilog/ICARUS/icarus_codes/3.png)

