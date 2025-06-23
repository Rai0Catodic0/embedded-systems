#Required #SyntaxAndStructureofC #software 
## Basic Usage
Data Pointers are the type used to store addresses.
Direct access can be done with:

### & address operator
Is used to signalize that we want the address of the variable and not its value
### * operator
Using is used to declare a pointer. 
```C
int x = 2; // address of x is 0x0802
int y = 3; // address of y is 0x08FF

int *p = &x; // p has value of 0x0802
p = &y; // p has value of 0x08FF
*p = 4; // now y has value of 4
```

## Pointers and arrays 
You can use a pointer to navigate through an array. By storing the start address of an array to a pointer.
```C
int x[5] = {1,2,3,4,5};
int *p = &x;
```
## Pointer Arithmetic 
Pointer can be incremented or decremented. When the you increase or decrease a pointer its value will change based on its type size. If you have a 16 bit int pointer and increment it, the address stored in the pointer will increase by 16 at a time. The same for decreasing. 

![[Pasted image 20250616161841.png]]
## Pointer Jumps

A pointer jump is increasing a pointer value for more than one.
```C
int x[6];
int *p = &x;

p += 2; // will increase the pointer by 32, or set its address to x[2]
```



## Double Pointers

Pointers can point to a point. Basically a double pointer is a pointer that points to the address of a pointer.

```C
int x = 10;
int *p = &x; // this points to x

int **pp = &p; // this points to the pointer p that points to x
```