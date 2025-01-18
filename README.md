# samsung-riscv

"RISC-V Development Training Program by VSD, in collaboration with Samsung Semiconductor India Research (SSIR) and Agastya International Foundation. A hands-on journey into open-source RISC-V processor design."

## Authour's info:
- Name: Hoysaleshwari U
- College: SJBIT,Bengaluru
- e-mail id: hoysaleshwaiu@gmail.com
- linkedin id: www.linkedin.com/in/hoysaleshwariu
- github profile: https://github.com/Hoysa

<details>
  <summary>Task1</summary>
  <br>
  
**Setting Up the RISC-V Toolchain.**



The task is to set up the essential tools for the RISC-V Talent Development Program, including installing Ubuntu 18.04 LTS (Bionic Beaver, 64-bit) on Oracle VirtualBox  and configuring the system with VS C++ Redistributable.

- **Oracle VirtualBox**

Oracle VirtualBox is a free, open-source virtualization software that allows users to run multiple operating systems on a single machine. It supports Windows, Linux, macOS, and other platforms, enabling the creation of virtual machines (VMs) for testing, development, or learning purposes.

![Screenshot 2025-01-07 002808](https://github.com/user-attachments/assets/97b2fb22-db4d-44e1-8541-65dd34863e26)

- **Visual studio C++ Redistributable**

The Visual Studio C++ Redistributable is a set of runtime libraries required to run applications developed with Microsoft Visual C++. It provides components like the C Runtime (CRT) and Standard C++ Library, ensuring compatibility and proper execution of C++ programs on Windows, even without Visual Studio installed.
![Screenshot 2025-01-07 002913](https://github.com/user-attachments/assets/1264bcac-0e1f-4d60-94bd-b562232018e3)

**To write and execute a simple C program to calculate the sum of numbers from 1 to n**
## **Steps and Process**

### **Step 1: Writing and Compiling Programs**
1. **Program Creation:**
   - Developed programs using a high-level programming language, such as C.
   - Ensured the source code was validated for correctness before proceeding further.

2. **Compilation:**
   - Utilized the RISC-V GCC compiler to convert the high-level code into RISC-V binaries.
   - Explored multiple compiler optimization flags (`-O0`, `-O1`, `-O2`, `-O3`) to observe differences in instruction generation, binary size, and efficiency.

***Key Steps***:
Open a Text Editor: The leafpad text editor is used to create a new file or edit an existing one.

***The command for opening the editor:***
<br>
````leafpad sum1ton.c````
<br>
***The C code for the sum of 1 to n number***
````#include <stdio.h>
int main()
 {
    int i, sum = 0, n = 5;
    for (i = 1; i <= n; ++i) {
        sum += i;
    }
    printf("Sum of numbers from 1 to %d is %d", n, sum);
    return 0;
}
````
**Compile the C program with GCC:**

````gcc sum1ton.c -o output````

**Run the compiled program:**

````.\a.out````


<br>![Screenshot 2025-01-06 231923](https://github.com/user-attachments/assets/a0006d2a-6499-4abe-9a57-0455328390b9)

**STAGE 2**: **Running the programm using RISCV compiler**
***command to compile in RISCV:***
<br>


````riscv64-unknown-elf-gcc-O1  -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c````
<br>

![Screenshot 2025-01-07 000802](https://github.com/user-attachments/assets/cb057ca5-d435-45c0-ae58-cf2aa388a49a)

***command for assembly code for the above***
<br>

````riscv64-unknown-elf-objdump -d sum1ton.o````
<br>


after that find the main section by writing ````/main````
<br>
and calculate no. of instruction in main section and compare the same by modifying the command .
<br>

***Modified Command***
<br>

````riscv64-unknown-elf-gcc-Ofast  -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c````


and then caluculate the no. of instruction.

![Screenshot 2025-01-07 000717](https://github.com/user-attachments/assets/7b9f284a-71d3-4157-906f-19eb3fa94d0f)


</details>


<details>
  <summary>Task2</summary>

## **Objective**
Focused on exploring the RISC-V architecture by writing, compiling, executing, and debugging programs. The goal was to analyze program behavior at the instruction level and gain practical experience with RISC-V tools and debugging workflows.

---

## **Steps and Process**

### **Step 1: Writing and Compiling Programs**
1. **Program Creation:**
   - Developed programs using a high-level programming language, such as C.
   - Ensured the source code was validated for correctness before proceeding further.
![Screenshot 2025-01-18 215938](https://github.com/user-attachments/assets/3f6c4994-8970-4657-8cb7-f3560a9903d5)

2. **Compilation:**
   - Utilized the RISC-V GCC compiler to convert the high-level code into RISC-V binaries.
     ![Screenshot 2025-01-18 224756](https://github.com/user-attachments/assets/8ac410a8-1ed3-468c-91ca-c1ff31c6ee20)


### **Step 2: Running Programs on Spike Simulator**
1. **Simulator Execution:**
   - The Spike simulator, a RISC-V ISA simulation tool, was employed to run the compiled binaries.
   - Verified the output and functionality of the program during simulation.

2. **Output Observation:**
   - Observed initial outputs during execution to ensure alignment with expected program behavior.

### **Step 3: Debugging Using Spike Simulator**
1. **Initiating Debugging:**
   - Launched the debugging environment using the `spike d` command.
   - Began debugging with a focus on analyzing the program’s instruction-level execution.
     ![Screenshot 2025-01-18 215801](https://github.com/user-attachments/assets/c38455cd-fe3c-4a59-9e02-3f622c900e04)


2. **Step-by-Step Analysis:**
   - Manually stepped through each instruction while monitoring the state of the program counter (PC).
   - Observed and documented changes in register and memory values for each executed instruction.
   - Validated the output at each stage to ensure the expected behavior was achieved.
![Screenshot 2025-01-18 215841](https://github.com/user-attachments/assets/479883a0-1b91-4c40-a398-ab82d31252bd)

3. **Understanding Optimization Impacts:**
   - Compared instruction-level behavior across binaries compiled with different optimization levels.
   - Identified how optimizations affected the program structure, such as loop unrolling, conditional execution, and reduced instruction count.


## **Tools Used**

### 1. **RISC-V GCC Compiler**
- Utilized for compiling high-level source code into RISC-V binaries.
- Supported experiments with various optimization flags to study their effects on performance and binary size.

### 2. **Spike Simulator**
- Provided a simulated RISC-V environment for executing and debugging programs.
- Enabled step-by-step instruction analysis and output verification.

---

## **Execution Workflow Visualization**

1. **Running the Program in Spike Simulator:**
   - Demonstrates the execution of the RISC-V binary within the simulator, showing initial outputs.

2. **Debugging Instructions Using `spike d`:**
   - Highlights the step-by-step debugging process, including key instructions and PC values.

3. **Manual Instruction Analysis:**
   - Depicts how each instruction was verified manually to ensure correctness and expected program behavior.

---

## **Conclusion**
 In Task 2  into RISC-V architecture and execution workflows.The following were achieved:
- A thorough understanding of how high-level code is translated into machine instructions.
- Enhanced skills in debugging and analyzing program behavior at the instruction level.
- Familiarity with key RISC-V tools like the Spike simulator and GCC compiler.

</details>
