#Required #software #AdvancedC 

## Enumerations 
*Definition*: Enumerations are integer data types that you can create with a limited range of 
values. Each value is represented by a symbolic constant that may be used in conjunction with variables of the same enumerated type.
Enumerations :
- are unique integer data types 
- May only contain a specifies list o values
- Values are specified as symbolic constants
-  Not necessary for writing C but can make code more readable

### How to create an Enumeration

```
enum type name { label0 = const0, ..., labelN=constN} 
enum peole {rob, steve, paul=7, bill};
// label values rob = 0 steve=1, paul=7, bill=8

enum weekday {sun, mon, tue, wed, thr, fri, sat} today;
enum weekday day; // today and day are variables if type weekday

typedef enum {sun, mon, tue, wed, thr, fri, sat} weekday;
enum weekday day;

day = wed;
day = 6;
if (day == wed){
	...
}

```

## State Machines
A [[State Machines]] is the framework for your code
- a state machine store the status of somethings at any given time
- state machine firmware is the code that controls the status at any given time 
- state machine firmware will step through the functionality states of the device
![[Pasted image 20250618225758.png]]
StateMachine with enum

```
typedef enum { SLEEP_WAIT, CHECK_ADC, MOTOR_ON, MOTOR_OFF} stateMachine;

stateMachine vacuumState;
switch(vacuumState){
	case SLEEP_WAIT:
		vacuumState++;
		...
	case CHECK_ADC:
		vacuumState++;
		...
}
```
![[Pasted image 20250618230426.png]]
![[Pasted image 20250618230401.png]]![[Pasted image 20250618230445.png]]
![[Pasted image 20250618230530.png]]
![[Pasted image 20250618230709.png]]
