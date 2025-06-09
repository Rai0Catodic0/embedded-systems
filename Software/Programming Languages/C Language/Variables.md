#Required #SyntaxAndStructureofC 
Variables are used to store data that can be accessed and modified, a variable must have a type and a name. 

# types
as said before, all variables must have a type, the basic types for variables are :
![[Pasted image 20250609014740.png]]

# Data Modifiers/specifiers
all data types have modifiers, they may or may not be specified on code, when they are not specified the compiler will choose one for you
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
    
    
# Custom data types

Typedef keyword can be used to create personalized datatypes based on the basic ones 
for example, we can create an unsigned 16 bits int type by writing
```
typedef usigned int uint16_t;
```


the typedef can be used more comprehensible data type names .

# Header Files

for large and complex code we should use header files to store declarations of [[function]] s and variable. header files use .h extension and should be included in the .C file whew you define the information declared in the header file.  there are two ways of including your header files

## ""

```
#include "main.h"
```

looks in the project directory for the header file
## <>

```
#include <math.h>
```
looks in the compiler include path for the header file