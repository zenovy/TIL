If there are multiple true/false flags, e.g. if the program runs multiple processes and wants to test the success/failure of each one, then we can use a binary code to represent a unique combination:

```
var flags = 0;
var FLAG_A = 1; // === 0001, since 2^0 = 1
var FLAG_B = 2; // === 0010, since 2^1 = 2
var FLAG_C = 4; // === 0100, etc...
var FLAG_D = 8; // === 1000
```

If we 'OR' the flags variable with any of the FLAG constants, it will contain all the flag information:

```
flags |= FLAG_A; // === 0001
// ... later ...
flags |= FLAG_D; // === 1001 
```

In the above example, we know that FLAG_A and FLAG_D have been set.

To see if a certain flag has been set, all we have to do is '&' the flag's value with our flag variable:

```
flags = 5;
if (flags & FLAG_C) {/*...*/} // will evaluate to true, since 0101 & 0100 === 0100, which is non-zero and therefore truthy
```

*Note*: If the flags were not powers of two, this would not work, since the use of OR presumes the flag values are mutually exclusive. 

