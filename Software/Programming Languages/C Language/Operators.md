#Required  #software #SyntaxAndStructureofC 

## Type Conversion

### Implicit type conversion

When performing an operation between two different types, it will promote one of the operators to match the  largest operator type. for instance:
```
float y = 2;
int x = 5;
float anwser;

anwser = x/y; // == 2.5
```

####  Implicit Type Conversion Hierarchic
![[Pasted image 20250615180306.png]]
## Assignment Operators

Assignment operator is the = used to assignment values to variables. but it can take other forms
### Compound operators 
![[Pasted image 20250615180704.png]]

## Simple Trick For Relational Operators

to avoid confusion between the relational and assignment operators place the literal on the left side of the operator:
```
if ( x = 10){ // will yield false only if x == 0
	// code
}

if (10 = x){ // will yield an sytaxe error
	// code
}
if (10 == x){ // will yield the expected behavior
	// code
}
```

## Logical Operators 

### and 
the '&&' is the C operator for the and logical operator 
```
if (x && y){ // will yield true when both x and y are true
	// code
}
```
### or 

the '||' is the and operator

```
if (y || x){ // will yield true when y or x are true
	// code
}
```
### not 

the not operator is expressed with "!" character
```
!x // will be true if x is false
```

## Bitwise Operator

### bitwise and  &
for x and y, performs an and operation between each of the correspondent bit of each operands
```
char x = 0b00001011;
char y = 0b00000101;
char awnser;

void main (void){
 awnser = x & y; // 0b00000001
}
```
### bitwise or | 
for x and y, performs an or operation between each of the correspondent bit of each operands
```
char x = 0b00001011;
char y = 0b00000101;
char awnser;

void main (void){
 awnser = x | y; // 0b00001111
}
```
### bitwise xor ^ 
for x and y, performs a xor operation between each of the correspondent bit of each operands
```
char x = 0b00001011;
char y = 0b00000101;
char awnser;

void main (void){
 awnser = x ^ y; // 0b00001110
}
```
### bitwise not ~
for x , performs a not operation for each of the correspondent bit of the operand 
```
char x = 0b00001011;
char y = 0b00000101;
char awnser;

void main (void){
 awnser = ~x // 0b1110100;
}
```


### masking 
masking is used to discover a status of one or more bits from a variable by comparing a know bit combination with the value:

example:
![[Pasted image 20250615183248.png]]

## Bitwise Shift Operator
left shift multiple a value by 2
right shift divide a value by 2.
### Left shift << 
shifts the bits of x, to the left n times (ie. n = 1)
```
char x = 0b00000101; // 5
char y;

void main (void){  
	y = x << 1; // 0b00001010
}
```


### Right shift >>
shifts the bits of x, to the right n times (ie. n = 1), for this operators we have a Sign Extension
if you right shift and the value is negative we put a 1 in the new location instead of a 0
```
char x = 0b00000101; // 5
char y = 0b11111010;

void main (void){  
	x = x >> 1; // 0b0000010
	y = y >> 1; // 0b1111101
}
```
## Cast Operator
when you use a cast operator you can temporarily cast a value to another type by:
```
int a = 10;
int b = 4;
float c;
c = (float)a/b; // 2.5
```

## Precedence and Associativity  

the operator precedence is : ( is better to use parenthesis)
![[Pasted image 20250615185450.png]]