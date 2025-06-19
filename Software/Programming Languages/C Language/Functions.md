#Required #software #SyntaxAndStructureofC 
Functions are pieces of code that receives parameters and returns a value.
Functions are defined like this :
```
ReturnType FunctionName(ParametersType1 ParameterName1,ParametersTypeN ParameterNameN){
	declarations 
	statements
	return ReturnValue;
}
```
Parameters names are only valid inside the function. 
Variables declared inside the Function only exists inside the function. this is called scope variables.
It can have multiple returns statements but all must return the same type.
the function ends when a return statements is executed.
## functions prototypes 
function prototypes is a declaration of the function return type, name and its parameters. 

# Function Pointers
- [[Pointers]] can be used to point to functions
- provides a flexible way to call functions 
- allows to pass function address to other functions
- Help make cleaner and more structured code
```
int (*fp)(int x); // name fp, * indicates the pointer, takes on int parameter and returns a int value. can only return one value
```

initialized by:
```
int  (*fp)(int x); // function pointer
int foo(int x); // function prototype

fp = &foo; // fp pointes to foo
```
### Function pointers as function parameters 

to pass a function pointer as a parameter use this syntax
```
int foobar(int a, int b,int (*fp)(int, int)){
	return fp(a, b);
}
```

### Array of Function pointers

- all functions on an array of function pointers must return the same type and receive the same number of parameters of the same type .
initializing the function pointer array like this will make the pointer point to the program memory
![[Pasted image 20250618230314.png]]