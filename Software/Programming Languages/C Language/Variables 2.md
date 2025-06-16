#Required #software  #SyntaxAndStructureofC 

## Multi File Project

Variables scope is define by where they are placed in C code. A variable can be local or global.
### Global
variables declared outside of any brackets are considered global and follow this behavior:
-  their values are retained during the whole life cycle of the program
-  they can be accessed from any point of the program .
### Local
Local variables are declared inside a bracket and are not valid outside of that bracket. unless the local variable is declared differently( ie. [[#Static Variables]]) their values will be destroyed at the end of that bracket.  


## Register Variable
A variable declared with the modifier Register is used to access a processor register immediately 
since the register in a micro-controller are easily accessible, this modifier is not necessary.
## Static Variables
a static variables has these characteristics:
- its address is permanent
- their value always exists from begging to end in the program.
- they are restricted to scope, but its value is maintained from function call to function call
- it can only be initialized once 

## Automatic Variables

any variable declared as a parameter or inside of a function is an automatic variable
- it exists only within the function
- they are freshly allocated for each function call
-  for micro controllers compilers a variable can be set as default automatic or [[#Static Variables]]

## External Variables
 to access variables that are defined elsewhere we need to use the external keyword to 
 tell the compiler how to handle that variable. when using the external keyword to declare a variable it wont allocate more memory for that variable since it already allocated it in another part of the code.

## Function Scope

[[Functions]] can have two storage classes:
- Static:  only accessible in the file where is located
- External: is accessible in any file in the project
Default is global and external.



