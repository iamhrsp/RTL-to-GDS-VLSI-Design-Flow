# Introduction to Bambu HLS

## What is Bambu?

Bambu is an **open-source High-Level Synthesis (HLS) tool** that translates high-level programming languages like **C/C++** into hardware descriptions, such as Verilog or VHDL, which can be used to implement designs on FPGAs and ASICs. It enables the automatic generation of efficient hardware from software-level descriptions, making it a key tool for **hardware-software co-design**.

---

## In Short:

- **High-Level to RTL Translation**: Converts C/C++ code into Register Transfer Level (RTL) descriptions for hardware implementation.
- **FPGA and ASIC Support**: Generates hardware that can be synthesized for FPGAs and ASICs.
- **Open-Source**: Freely available for use and modification, making it ideal for academic and research purposes.

---

## Why Use Bambu?

Bambu simplifies the hardware design process by allowing users to describe functionality in a high-level language. This reduces the learning curve for hardware design and accelerates the development process. It is especially beneficial for tasks like:

- Developing hardware accelerators for computation-intensive applications.
- Exploring design-space trade-offs for area, power, and performance.
- Integrating hardware designs into larger systems.

---

## How Does Bambu Work?

1. **Input**: The user provides C/C++ code that describes the functionality to be implemented in hardware.
2. **Processing**: Bambu analyzes the code and generates an equivalent RTL design optimized for the target hardware.
3. **Output**: The tool produces Verilog or VHDL code, ready for synthesis or simulation.

---


# Installation of Bambu HLS

### Objective
To gain hands-on experience with **High-Level Synthesis (HLS)** using **Bambu HLS**.

---
### Assuming you have a Linux Distribution installed on your system. I use Ubuntu.
--- 

1. **Update package index files on the system:**
   ```bash
   sudo apt-get update
   ```

2. **Install dependencies required by Bambu HLS tool:**
   ```bash
   sudo apt-get install -y --no-install-recommends build-essential ca-certificates gcc-multilib git iverilog verilator wget
   ```

3. **Download the AppImage:**
   ```bash
   wget https://release.bambuhls.eu/appimage/bambu-0.9.7.AppImage
   ```

4. **Make the AppImage executable:**
   ```bash
   chmod +x bambu-0.9.7.AppImage
   ```

5. **Install FUSE (File system in userspace):**
   ```bash
   sudo add-apt-repository universe
   sudo apt install libfuse2
   ```
   Once it is done, Bambu installation completion can be checked using this command ```./bambu-0.9.7.AppImage```

6. **Run the tool:**
   ```bash
   ./bambu-0.9.7.AppImage <path-to-c-file> --top-fname=<accelerator-function-to-be-implemented-in-hardware>
   ```
   Path to the C file should be given. Moreover, the function (say a top level file) to be synthesised should also be given. For example, in the C example below ```func``` goes in place of ```<accelerator-function-to-be-implemented-in-hardware>```
---

## Example
**Input C code for generating Verilog RTL using HLS tool:**

```c
long func(int, int, int, int);
main()
{
    int j;
    int k;
    int c;
    int d;
    int res = func(j, k, c, d);
    return 0;
}

long func(int j, int k, int c, int d)
{
    int i = 0;
    if (c > 2) {
        i = j - k;
    } else if (d < 5) {
        i = j + k;
    } else {
        i = 12;
    }
    return i;
}
```

---

## Additional Resources.

- **Documentation**: [Official Bambu HLS Documentation](https://panda.dei.polimi.it/?page_id=81)
- **Source Code**: [GitHub Repository](https://github.com/ferrandi/PandA-bambu)
- **Tutorial**: [Bambu Tutorial](https://panda.dei.polimi.it/?page_id=555)
- [Open Source HLS Tools - ResearchGate](https://www.researchgate.net/publication/315383441_Open_Source_HLS_Tools_A_stepping_stone_for_modern_Electronic_CAD)
- [Bambu Framework for Memory-Intensive Applications - ResearchGate](https://www.researchgate.net/publication/261299590_Bambu_A_modular_framework_for_the_high_level_synthesis_of_memory-intensive_applications)

---

