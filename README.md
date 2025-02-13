# samsung-riscv

"RISC-V Development Training Program by VSD, in collaboration with Samsung Semiconductor India Research (SSIR) and Agastya International Foundation. A hands-on journey into open-source RISC-V processor design."

## Authour's info:
- Name: Hoysaleshwari U
- College: SJBIT,Bengaluru
- e-mail id: hoysaleshwaiu@gmail.com
- linkedin id: www.linkedin.com/in/hoysaleshwariu
- github profile: https://github.com/Hoysa

<details>
  <summary>Task1 : Introduction to RISC-V Architecture and Compilation Workflow</summary>
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
  <summary>Task2 : Exploring RISC-V Through Program Debugging</summary>

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


<details>
  <summary>Task3 : RISC-V Instruction Set Breakown</summary>

---

## **1. Overview of RISC-V Instructions**
RISC-V is a simple and modular instruction set architecture (ISA). Instructions in RISC-V are 32 bits long (fixed width) and organized into six standard formats: **R-Type**, **I-Type**, **S-Type**, **B-Type**, **U-Type**, and **J-Type**. These formats define the fields in an instruction.

Each instruction contains the following **fields**:
1. **Opcode**: Specifies the type of instruction (e.g., load, store, arithmetic).
2. **rd**: Destination register (where the result is stored).
3. **rs1, rs2**: Source registers (used in operations or memory access).
4. **funct3, funct7**: Specify the exact operation for certain opcodes.
5. **Immediate (imm)**: A constant value embedded in the instruction.
6. **Offset/Address**: Used in memory or control transfer instructions.

---

## **2. Detailed Breakdown of Instruction Formats**

### **R-Type (Register-Register Instructions)**
- Used for operations between registers (e.g., addition, subtraction).
- **Fields**:  
  - **opcode** (7 bits): Identifies the type of instruction.  
  - **rd** (5 bits): Destination register.  
  - **funct3** (3 bits): Subclassifies the operation (e.g., add vs. subtract).  
  - **rs1** (5 bits): First source register.  
  - **rs2** (5 bits): Second source register.  
  - **funct7** (7 bits): Further subclassifies the operation.  

#### Example: `add a0, a1, a2`  
- Add contents of `a1` and `a2`, store the result in `a0`.  
- **Encoding**:  
  - `opcode`: `0110011` (arithmetic operation).  
  - `rd`: `a0` (x10 = 01010).  
  - `funct3`: `000` (add operation).  
  - `rs1`: `a1` (x11 = 01011).  
  - `rs2`: `a2` (x12 = 01100).  
  - `funct7`: `0000000` (add-specific).  
- **Final Encoding**: `0x00c50533`

---

### **I-Type (Immediate Instructions)**
- Used for operations with immediate values and memory loads.
- **Fields**:  
  - **opcode** (7 bits): Instruction type (e.g., load or arithmetic).  
  - **rd** (5 bits): Destination register.  
  - **funct3** (3 bits): Subclassifies the operation.  
  - **rs1** (5 bits): Source register.  
  - **imm[11:0]** (12 bits): Immediate value (signed).  

#### Example: `addi sp, sp, -16`  
- Add immediate value `-16` to `sp`.  
- **Encoding**:  
  - `opcode`: `0010011` (immediate arithmetic).  
  - `rd`: `sp` (x2 = 00010).  
  - `funct3`: `000` (add immediate).  
  - `rs1`: `sp` (x2 = 00010).  
  - `imm`: `-16` (12-bit signed = `111111111000`).  
- **Final Encoding**: `0xfff10113`

---

### **S-Type (Store Instructions)**
- Used to store a register value into memory.
- **Fields**:  
  - **opcode** (7 bits): Instruction type (store).  
  - **imm[11:5]** (7 bits): Upper 7 bits of the immediate value.  
  - **rs2** (5 bits): Source register to be stored.  
  - **rs1** (5 bits): Base address register.  
  - **funct3** (3 bits): Operation subclass.  
  - **imm[4:0]** (5 bits): Lower 5 bits of the immediate value.  

#### Example: `sd ra, 8(sp)`  
- Store the value of `ra` at the memory address `sp + 8`.  
- **Encoding**:  
  - `opcode`: `0100011` (store operation).  
  - `imm[11:5]`: `0000000` (from `8`, split upper bits).  
  - `rs2`: `ra` (x1 = 00001).  
  - `rs1`: `sp` (x2 = 00010).  
  - `funct3`: `011` (store doubleword).  
  - `imm[4:0]`: `01000` (from `8`, split lower bits).  
- **Final Encoding**: `0x00813023`

---

### **B-Type (Branch Instructions)**
- Used for conditional branching.
- **Fields**:  
  - **opcode** (7 bits): Instruction type (branch).  
  - **imm[12]** (1 bit): Immediate value MSB.  
  - **imm[10:5]** (6 bits): Middle bits of immediate value.  
  - **rs1** (5 bits): First source register.  
  - **rs2** (5 bits): Second source register.  
  - **funct3** (3 bits): Branch condition.  
  - **imm[4:1]** (4 bits): Lower bits of immediate value.  
  - **imm[11]** (1 bit): Immediate value LSB.  

#### Example: `beq a0, a1, 16`  
- Branch to `PC + 16` if `a0 == a1`.  
- **Encoding**:  
  - `opcode`: `1100011` (branch).  
  - `imm[12]`: `0`.  
  - `imm[10:5]`: `000001`.  
  - `rs1`: `a0` (x10 = 01010).  
  - `rs2`: `a1` (x11 = 01011).  
  - `funct3`: `000` (branch if equal).  
  - `imm[4:1]`: `0001`.  
  - `imm[11]`: `0`.  
- **Final Encoding**: `0x01050863`

---

### **U-Type (Upper Immediate Instructions)**
- Used to load a 20-bit immediate into the upper 20 bits of a register.
- **Fields**:  
  - **opcode** (7 bits): Instruction type.  
  - **rd** (5 bits): Destination register.  
  - **imm[31:12]** (20 bits): Immediate value.  

#### Example: `lui a0, 0x21`  
- Load `0x21` into the upper 20 bits of `a0`.  
- **Encoding**:  
  - `opcode`: `0110111` (load upper immediate).  
  - `rd`: `a0` (x10 = 01010).  
  - `imm[31:12]`: `0x21`.  
- **Final Encoding**: `0x00210537`

---

### **J-Type (Jump Instructions)**
- Used for unconditional jumps and storing return addresses.
- **Fields**:  
  - **opcode** (7 bits): Instruction type (jump).  
  - **rd** (5 bits): Destination register.  
  - **imm[20]** (1 bit): Immediate MSB.  
  - **imm[10:1]** (10 bits): Middle bits of the immediate.  
  - **imm[11]** (1 bit): Immediate bit 11.  
  - **imm[19:12]** (8 bits): Remaining bits of the immediate.  

#### Example: `jal ra, 10484`  
- Jump to `PC + 10484` and save return address in `ra`.  
- **Encoding**:  
  - `opcode`: `1101111` (jump and link).  
  - `rd`: `ra` (x1 = 00001).  
  - Immediate: Split `10484` into the fields:  
    - `imm[20]`: `0`, `imm[10:1]`: `0100011101`, `imm[11]`: `0`, `imm[19:12]`: `00101000`.  
- **Final Encoding**: `0x28c000ef`

---

 

---

## **RISC-V Instruction Formats**
RISC-V instructions are 32 bits wide and use several standard formats. These formats define how the binary instruction is divided into fields for operation codes (opcodes), registers, immediate values, and function identifiers.  

### **Key Instruction Formats**
| **Format** | **Description**                                           | **Fields**                                               |
|------------|-----------------------------------------------------------|----------------------------------------------------------|
| **R-Type** | Register-register operations                              | opcode, rd, funct3, rs1, rs2, funct7                     |
| **I-Type** | Immediate value operations and loads                      | opcode, rd, funct3, rs1, imm[11:0]                       |
| **S-Type** | Store instructions                                        | opcode, imm[11:5], rs2, rs1, funct3, imm[4:0]            |
| **B-Type** | Conditional branches                                      | opcode, imm[12], imm[10:5], rs1, rs2, funct3, imm[4:1]   |
| **U-Type** | Upper immediate (load a 20-bit immediate)                 | opcode, rd, imm[31:12]                                   |
| **J-Type** | Unconditional jumps                                       | opcode, rd, imm[20], imm[10:1], imm[11], imm[19:12]      |

---

## **Instruction Breakdown and Examples**
Here are 15 unique RISC-V instructions, including their type, explanation, components, and final encoding.

| **#** | **Instruction**         | **Type** | **Explanation**                                                                                       | **Fields**                                                                                                                                               | **Encoding (Hex)** |
|-------|--------------------------|----------|-------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|
| 1     | `lui a0, 0x21`           | U-Type   | Load 20-bit immediate value (shifted left by 12) into upper 20 bits of `a0`.                          | **opcode**: `0110111`, **rd**: `a0` (x10), **imm[31:12]**: `0x21`.                                                                                       | `0x00210537`       |
| 2     | `addi sp, sp, -16`       | I-Type   | Add immediate value (-16) to `sp`.                                                                   | **opcode**: `0010011`, **rd**: `sp` (x2), **rs1**: `sp` (x2), **imm[11:0]**: `-16`.                                                                      | `0xfff10113`       |
| 3     | `add a0, a0, a1`         | R-Type   | Add contents of `a0` and `a1`, store result in `a0`.                                                 | **opcode**: `0110011`, **rd**: `a0` (x10), **rs1**: `a0` (x10), **rs2**: `a1` (x11), **funct3**: `000`, **funct7**: `0000000`.                             | `0x00b50533`       |
| 4     | `sd ra, 8(sp)`           | S-Type   | Store the value in `ra` to memory at `sp + 8`.                                                       | **opcode**: `0100011`, **rs1**: `sp` (x2), **rs2**: `ra` (x1), **imm[11:0]**: `8` (split into `imm[11:5]` and `imm[4:0]`).                                | `0x00813023`       |
| 5     | `jal ra, 10484`          | J-Type   | Jump to address (PC + 10484) and save return address in `ra`.                                        | **opcode**: `1101111`, **rd**: `ra` (x1), **imm[20:0]**: `10484` (split into `imm[20]`, `imm[10:1]`, `imm[11]`, and `imm[19:12]`).                        | `0x28c000ef`       |
| 6     | `li a1, 5`               | I-Type   | Load immediate value 5 into `a1`.                                                                    | **opcode**: `0010011`, **rd**: `a1` (x11), **rs1**: `x0` (hardwired to 0), **imm[11:0]**: `5`.                                                           | `0x00500893`       |
| 7     | `mv a0, a2`              | I-Type   | Move contents of `a2` to `a0` (pseudoinstruction for `addi a0, a2, 0`).                              | **opcode**: `0010011`, **rd**: `a0` (x10), **rs1**: `a2` (x12), **imm[11:0]**: `0`.                                                                      | `0x00060513`       |
| 8     | `ecall`                  | I-Type   | Perform a system call.                                                                                | **opcode**: `1110011`, **funct3**: `000`, **rd**, **rs1**, and **imm[11:0]**: All zeros.                                                                 | `0x00000073`       |
| 9     | `ld ra, 8(sp)`           | I-Type   | Load value from memory at `sp + 8` into `ra`.                                                        | **opcode**: `0000011`, **rd**: `ra` (x1), **rs1**: `sp` (x2), **imm[11:0]**: `8`.                                                                        | `0x00813003`       |
| 10    | `add sp, sp, 16`         | I-Type   | Add immediate value 16 to `sp`.                                                                      | **opcode**: `0010011`, **rd**: `sp` (x2), **rs1**: `sp` (x2), **imm[11:0]**: `16`.                                                                       | `0x01010113`       |
| 11    | `ret`                    | I-Type   | Return from a function (pseudoinstruction for `jalr x0, 0(ra)`).                                      | **opcode**: `1100111`, **rd**: `x0`, **rs1**: `ra` (x1), **imm[11:0]**: `0`.                                                                             | `0x00008067`       |
| 12    | `auipc a5, 0xFFFF0`      | U-Type   | Load PC-relative 20-bit immediate value into `a5`.                                                   | **opcode**: `0010111`, **rd**: `a5` (x15), **imm[31:12]**: `0xFFFF0`.                                                                                    | `0xFFFFF797`       |
| 13    | `addi a5, a5, -220`      | I-Type   | Add immediate value (-220) to `a5`.                                                                  | **opcode**: `0010011`, **rd**: `a5` (x15), **rs1**: `a5` (x15), **imm[11:0]**: `-220` (12-bit signed value).                                             | `0xFCF78313`       |
| 14    | `beq a0, a1, 16`         | B-Type   | Branch to PC + 16 if `a0` equals `a1`.                                                               | **opcode**: `1100011`, **rs1**: `a0` (x10), **rs2**: `a1` (x11), **imm[12:1]**: `16` (split into `imm[12]`, `imm[10:5]`, `imm[4:1]`).                     | `0x01050863`       |
| 15    | `jalr ra, 0(sp)`         | I-Type   | Jump to address in `sp` and save return address in `ra`.                                             | **opcode**: `1100111`, **rd**: `ra` (x1), **rs1**: `sp` (x2), **imm[11:0]**: `0`.                                                                        | `0x00013067`       |

---

### **Detailed Explanation of Encoding Steps**
- **Immediate Values**: Handled differently depending on the instruction type (e.g., split into multiple fields in S-Type, B-Type, and J-Type).  
- **Registers**: Mapped to their binary equivalents (e.g., `a0 = x10 = 01010`).  
- **Opcodes and funct3/funct7**: Unique for each instruction and operation.  


 </details> 
<details>  <summary>Task4 : Functional Simulation of RISC-V Core </summary>

  # RISC-V Core Functional Simulation

"**Note**: Designing the RISC-V architecture and writing its testbench are not part of this skill development programme. Therefore, we will use the pre-designed Verilog code and testbench from the reference GitHub repository: iiitb_rv32i."

## Objective
The objective of this task is to perform the simulation of the RISC-V core using `hoysala_rv64i.v` (LogNetList) and `hoysala_rv64i_tb.v` (TestBench). The simulation involves compiling the Verilog files, generating a `.vcd` file, and observing the waveform in GTKWave.

---

## Project Structure
```
Hoysaleshwari/
|-- hoysala_rv64i.v            # Verilog netlist for the RISC-V Core
|-- hoysala_rv64i_tb.v         # Testbench for the RISC-V Core
|-- Makefile                   # Makefile for compilation and simulation
|-- waveforms/                 # Directory for waveform snapshots
    |-- *.png                  # Waveform images
```

---

## Tools Used
- **Icarus Verilog (iverilog):** Used for compiling and simulating Verilog design files.
- **GTKWave:** Used for viewing and analyzing waveform outputs.

---

## Steps to Perform Simulation

### 1. Setting up the Environment
Ensure you have the following installed:
- **Icarus Verilog:** For compiling and simulating Verilog files.
- **GTKWave:** For waveform analysis.

Install on Ubuntu:
```bash
sudo apt update
sudo apt install iverilog gtkwave
```

For Windows/MacOS, download and install [Icarus Verilog](https://github.com/steveicarus/iverilog) and [GTKWave](http://gtkwave.sourceforge.net/).

---

### 2. Compile and Simulate

- Compile `hoysala_rv64i.v` and `hoysala_rv64i_tb.v`.
- Generate the `hoysala_rv64i.vcd` waveform file.
- ![Screenshot 2025-01-26 101246](https://github.com/user-attachments/assets/beffc710-6a73-48d2-b81a-50e7bc045cb0)


---

### 3. View Waveforms
To open the waveform file, use GTKWave:
```bash
gtkwave hoysala_rv64i.vcd
```

---

## Results and Analysis

### Instructions Simulated
The waveforms were analyzed for the following instructions:

#### 1. ADD R6, R2, R1
- **Standard RISC-V ISA:** `32'h00110333`
- **Hardcoded ISA:** `32'h02208300`
- **Input Values:** R2 = 2, R1 = 1
- **Output Value:** R6 = 3
- **Analysis:** This instruction adds the values in registers R2 and R1, storing the result in R6.
- ![Screenshot 2025-01-25 223923](https://github.com/user-attachments/assets/7a15ab77-f07c-4164-87bf-eb49903f77ac)


#### 2. SUB R7, R1, R2
- **Standard RISC-V ISA:** `32'h402083b3`
- **Hardcoded ISA:** `32'h02209380`
- **Input Values:** R1 = 2, R2 = 3
- **Output Value:** R7 = FFFFFFFF (32-bit representation of -1)
- **Analysis:** This instruction subtracts the value in R2 from R1, resulting in a negative value represented in two's complement.
- ![Screenshot 2025-01-25 224003](https://github.com/user-attachments/assets/2b859212-c16a-4d90-8d76-c4c31da47dbf)


#### 3. AND R8, R1, R3
- **Standard RISC-V ISA:** `32'h0030f433`
- **Hardcoded ISA:** `32'h0230a400`
- **Input Values:** R1 = 2, R3 = 5
- **Output Value:** R8 = 1
- **Analysis:** Performs a bitwise AND operation between R1 and R3, storing the result in R8.
- ![Screenshot 2025-01-25 224042](https://github.com/user-attachments/assets/aac823d3-6f22-4781-9d5d-083d16e8d18a)


#### 4. OR R9, R2, R5
- **Standard RISC-V ISA:** `32'h005164b3`
- **Hardcoded ISA:** `32'h02513480`
- **Input Values:** R2 = 1, R5 = 4
- **Output Value:** R9 = 7
- **Analysis:** Performs a bitwise OR operation between R2 and R5, storing the result in R9.
- ![Screenshot 2025-01-25 224248](https://github.com/user-attachments/assets/3bd6e924-27e0-4c67-ad2d-cbb1c3a03f44)


#### 5. XOR R10, R1, R4
- **Standard RISC-V ISA:** `32'h0040c533`
- **Hardcoded ISA:** `32'h0240c500`
- **Input Values:** R1 = 2, R4 = 4
- **Output Value:** R10 = 5
- **Analysis:** Performs a bitwise XOR operation between R1 and R4, storing the result in R10.
- ![Screenshot 2025-01-25 224351](https://github.com/user-attachments/assets/b2be1d8c-feac-458e-bc67-8e1b1cd67409)


#### 6. SLT R1, R2, R4
- **Standard RISC-V ISA:** `32'h0045a0b3`
- **Hardcoded ISA:** `32'h02415580`
- **Input Values:** R2 = 4, R4 = 5
- **Output Value:** R1 = 1
- **Analysis:** Compares R2 and R4, setting R1 to 1 if R2 is less than R4.
- ![Screenshot 2025-01-25 224436](https://github.com/user-attachments/assets/443b4c44-baea-4b7f-8578-c71a9523c0ec)


#### 7. ADDI R12, R4, 5
- **Standard RISC-V ISA:** `32'h004120b3`
- **Hardcoded ISA:** `32'h00520600`
- **Input Values:** R4 = 1, Immediate = 2
- **Output Value:** R12 = 9
- **Analysis:** Adds the immediate value 5 to the contents of R4, storing the result in R12.
- ![Screenshot 2025-01-25 224526](https://github.com/user-attachments/assets/e3c32fc1-7ff9-48c5-9cb6-97cdde44f0aa)


#### 8. BEQ R0, R0, 15
- **Standard RISC-V ISA:** `32'h00000f63`
- **Hardcoded ISA:** `32'h00f00002`
- **Input Values:** R0 = 0, R0 = 0
- **Output Value:** Branch taken to offset 15
- **Analysis:** Compares R0 and R0. Since they are equal, a branch to the specified offset is executed.


#### 9. SW R3, R1, 2
- **Standard RISC-V ISA:** `32'h0030a123`
- **Hardcoded ISA:** `32'h00209181`
- **Input Values:** R3 = 6, R1 = Base Address, Offset = 2
- **Output Value:** Memory[Base Address + 2] = 6
- **Analysis:** Stores the value in R3 to the memory address calculated by adding the offset to R1.
- ![Screenshot 2025-01-25 224630](https://github.com/user-attachments/assets/ea609cd0-920d-422f-b0d5-24bd4b855c7f)


#### 10. LW R13, R1, 2
- **Standard RISC-V ISA:** `32'h0020a683`
- **Hardcoded ISA:** `32'h00208681`
- **Input Values:** R1 = Base Address, Offset = 2
- **Output Value:** R13 = Memory[Base Address + 2]
- **Analysis:** Loads the value from memory at the specified address into R13.

#### 11. SRL R16, R14, R2
- **Standard RISC-V ISA:** `32'h0030a123`
- **Hardcoded ISA:** `32'h00271803`
- **Input Values:** R14 = 16, R2 = 2
- **Output Value:** R16 = 4
- **Analysis:** Performs a logical right shift on the value in R14 by the amount specified in R2, storing the result in R16.

#### 12. SLL R15, R1, R2
- **Standard RISC-V ISA:** `32'h002097b3`
- **Hardcoded ISA:** `32'h00208783`
- **Input Values:** R1 = 1, R2 = 3
- **Output Value:** R15 = 8
- **Analysis:** Performs a logical left shift on the value in R1 by the amount specified in R2, storing the result in R15.

---

</details>

<details>
  <summary>Task5 : RISC-V Morse Decoder with LCD Display.</summary>


  ### Project Name:  
**RISC-V Morse Decoder with LCD Display**  

### Overview:  
This project uses a **RISC-V VSDSquadron Mini** board to translate **Morse code** input via a button into **English text**, which is displayed on an **I2C LCD screen**. This helps individuals unfamiliar with Morse code to read messages in real-time.  

---

## List of Components  
### Hardware:  
- **VSDSquadron Mini (RISC-V) Development Board**  
- **Push Button** (for Morse code input)  
- **I2C LCD Display** (16x2 or OLED)  
- **Resistors** (10kΩ for pull-down)  
- **Connecting Wires**  
- **Breadboard** (for easy prototyping)  
- **Power Supply (USB)**  

### Software:  
- **Ubuntu OS**  
- **RISC-V GCC Compiler**  
- **I2C Libraries for LCD**  



## Pin Details  
| **Component**  | **Pin Name**       | **VSDSquadron Mini Pin** |
|---------------|-------------------|-------------------------|
| **LCD (I2C)**  | VCC               | 3.3V / 5V              |
|               | GND               | GND                     |
|               | SDA               | PA9                     |
|               | SCL               | PA10                    |
| **Push Button** | One Terminal      | GND                     |
|               | Other Terminal    | PA1                     |

---

## Block Diagram

![Screenshot 2025-02-13 113414](https://github.com/user-attachments/assets/0b4ec213-d708-41b0-8ba1-1a2705c5805e)




## circuit diagram


![Screenshot 2025-02-13 150529](https://github.com/user-attachments/assets/78c1a28c-e4f7-4fb6-a956-5d285d243f41)

  </details>
