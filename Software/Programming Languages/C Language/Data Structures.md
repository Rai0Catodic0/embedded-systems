#Required #software #AdvancedC
## Structures
Structures are collections of variables grouped together under a common name. The variables within a structure are referred to as the structure's members, and may be accessed individually as needed.
The syntax for creating a structure is:
```
struct structName
{
	type1 memberName1;
	...
	typeN memberNameN;
};
```
to declare a structure we write:
```
struct complex
{
	float re;
	float im;
};

complex x,y;
```
accessing structure members can be do like
```
struct complex
{
	float re;
	float im;
}x,y;

int main(void)
{
	x.re = 1.26;
	x.im = 2.50;
	y = x;
}
// or
struct complex
{
	float re;
	float im;
};

int main(void)
{   struct complex x,y;
	x.re = 1.26;
	x.im = 2.50;
	y = x;
}
```

### typedef
you can create a structure with typedef keyword
```
typedef struct structTag{
	type1 memberName1;
	...
	typeN memberNameN;
}typeName
```
since you defined a type you no longer needs to use the keyword struct to declare instances of that structure
```
typeef struct complex
{
	float re;
	float im;
}complex;

int main(void)
{   complex x,y;
	x.re = 1.26;
	x.im = 2.50;
	// or
	x = {1.26, 2.50};
	y = x;
}
```

### bit Fields
are members of structures that occupy a specified number of adjacent bits. Compilers typically
determine the size of the variable that holds the bit field.
- Are ordinary members of a structure
- Have specified bit width
-  Are used in conjunction with structure to provide a access to a variable without masking operations. 
Bit fields are declared like
```
struct structName
{
	unsigned int memberName1: bitWidth;
	...
	typeN memberNameN;
}

typedef struct{
	unsigned int bit0: q;
	...
	typeN memberNameN;
}typeName
```
## Unions
Unions are similar to structures but the members of a union all share the same memory location.
In essence a union is a variable that is capable of holding different types of data at different times 
- It may contain any number of members 
- Members may be of any type
- Are as large as their largest member
```
union unionName
{
	type1 memberName1;
	...
	typeN memberNameN;
};
```

The typedef can also be used with unions

```
typedef union unionTag{
	type1 memberName1;
	...
	typeN memberNameN;
}typeName
```

### how union are alocated
![[Pasted image 20250616175954.png]]