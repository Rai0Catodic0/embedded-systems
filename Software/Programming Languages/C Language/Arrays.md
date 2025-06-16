#Required #SyntaxAndStructureofC #software 
## Basic Array and usage
arrays are variables that can store multiple items of the same type in a list like structure and can be declared like this 
```
type arrayName[size];
```
an array can be initialized like:
```
int a[5] = {10, 20, 30, 40, 50};
char b[5] = {'a', 'b', 'c', 'd', 'e'};
```
to access a array item by index like this
```
	arrayName[index]
```
the index must be within the array size or there will be a compiler error 
## Multidimensional Arrays
an array can have n dimensions, with n > 1. multidimensional arrays can be declared like this
```
type arrayName[size0][size1];
```
## Array processing
array are usually processed on loops like
```
int index = O;
int array[10];
while(index){
	array[index]=index;
	index++;
}
for(index; index>0; index--){
	array[index] = 0;
}
```
## Strings
Strings can be treated as an array of characters that ends with a \0.
