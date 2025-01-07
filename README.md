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

**STAGE1** :**To write and execute a simple C program to calculate the sum of numbers from 1 to n**

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
