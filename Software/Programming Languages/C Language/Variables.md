#Required #SyntaxAndStructureofC #software 
Variables are used to store data that can be accessed and modified, a variable must have a type and a name. 

# types
As said before, all variables must have a type, the basic types for variables are :
![[Pasted image 20250609014740.png]]

# Data Modifiers/specifiers
All data types have modifiers, they may or may not be specified on code, when they are not specified the compiler will choose one for you
## Signed or Unsigned
- **`signed`** (default for `int` and `char` in most implementations):
    - Can represent **positive and negative** values.
    - Uses **two’s complement** (most systems) for negative numbers.
    - **Bit allocation**: The **MSB (Most Significant Bit)** acts as the sign bit.
        - Example: `signed char` (8-bit):
            - Range: **-128 to 127** (`1` bit for sign, `7` bits for magnitude).
- **`unsigned`**
    - Only **non-negative** values (zero and positive).
    - **No sign bit**, so all bits contribute to magnitude.
        - Example: `unsigned char` (8-bit):
            - Range: **0 to 255** (all `8` bits for value).
## Short or Long
- **`short`**:
    - Requests a **smaller storage size** than `int` (but not larger).        
    - Typically **16-bit** (range: `-32,768` to `32,767` for `signed short`).
    - Used for **memory optimization** when full `int` range isn’t needed.
- **`long`**:
    - Requests **at least the size of `int`** (possibly larger).
    - Typically **32-bit** or **64-bit** (e.g., `-2,147,483,648` to `2,147,483,647` for `signed long`).
    - `long long` (C99+) is **at least 64-bit**.
    
## Type qualifiers
### volatile
The volatile keyword in C is a type qualifier used to inform the compiler that the value of a variable may change at any time, without any explicit action at any the program's code. This is particularly important in scenarios where external factors, such as hardware, interrupts service routines(ISRs), or other threads, can modify the variable's value.

Purpose and Effect:

- **Prevents Compiler Optimizations:**
    
    The primary purpose of `volatile` is to prevent the compiler from performing certain optimizations that might assume a variable's value remains constant between accesses. Without `volatile`, the compiler might cache the variable's value in a register and reuse it, leading to incorrect behavior if the value is modified externally.
    
- **Ensures Memory Access:**
    
    When a variable is declared `volatile`, the compiler is instructed to always fetch its value directly from memory each time it is accessed, and to write back to memory after each modification. This ensures that the program always works with the most up-to-date value.
    

Common Use Cases:

- **Memory-Mapped Hardware Registers:**
    
    In embedded systems, `volatile` is crucial for interacting with hardware registers whose values can change independently of the CPU's direct instructions (e.g., status registers, control registers).
    
- **Global Variables Modified by Interrupt Service Routines (ISRs):**
    
    If a global variable is shared between the main program flow and an ISR, declaring it `volatile` ensures that the main program sees the changes made by the ISR, and vice versa.
    
- **Variables Shared Between Threads (with limitations):**
    
    While `volatile` can help prevent certain compiler optimizations in multi-threaded environments, it does not provide thread safety or guarantee atomicity for complex operations. For robust thread synchronization, mechanisms like mutexes or atomic operations are required.
    
- **Loop Counters in Delays:**
    
    In some cases, `volatile` might be used for loop counters in busy-wait delays to prevent the compiler from optimizing away the loop if it appears to have no side effects.
# Custom data types

Typedef keyword can be used to create personalized datatypes based on the basic ones 
for example, we can create an unsigned 16 bits int type by writing
```
typedef usigned int uint16_t;
```


The typedef can be used more comprehensible data type names.

# Header Files

For large and complex code we should use header files to store declarations of [[Functions]] and variable. Header files use .h extension and should be included in the.C file whew you define the information declared in the header file. There are two ways of including your header files

## ""

```
#include "main.h"
```

Looks in the project directory for the header file
## <>

```
#include <math.h>
```
Looks in the compiler include path for the header file