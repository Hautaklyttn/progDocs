---
layout: default
---

{::options parse_block_html="true" /}  

[Back](../)  

&nbsp;

# Function Collection C
---  

&nbsp;

## Conversion functions  

### Hexadecimal-to-X

```c
#include <stdlib.h>

static long Hex2Dec(const char* hex) {
    long decimal = strtol(hex, NULL, 16);
    return decimal;
}
```

```c
#include <stdio.h>
#include <string.h>

// 'binContainer': "char container[1024]; memset(container, '\0', sizeof(container));"
static void Hex2Bin(const char* hex, char* binContainer) {
    const char binary[16][5] = {"0000", "0001", "0010", "0011", "0100", /
        "0101", "0110", "0111", "1000", "1001", "1010", "1011", "1100", /
        "1101", "1110", "1111"};

    char single;

    for (int j=0; j<strlen(hex); j++) {
        single = hex[j];
        strcat(binContainer, binary[Hex2Dec(&single)]);
    }
}
```

&nbsp;

### Binary-To-X

```c
#include <stdlib.h>

static long Bin2Dec(const char* binary) {
    long decimal = strtol(binary, NULL, 2);
    return decimal;
}
```

```c
// 'hexContainer': "char container[16]; memset(container, '\0', sizeof(container));"
static void Bin2Hex(const char* binary, char* hexContainer) {
	long decimal = Bin2Dec(binary);
	Dec2Hex(decimal, hexContainer);
}
```

&nbsp;

### Decimal-To-X  

```c
#include <stdio.h>

// 'hexContainer': "char container[16]; memset(container, '\0', sizeof(container));"
static void Dec2Hex(const int decimal, char* hexContainer) {
    sprintf(hexContainer, "%x", decimal);
}
```

```c
#include <stdio.h>

static unsigned int Dec2Bin(unsigned int k) {
    return (k == 0 || k == 1 ? k : ((k % 2) + 10 * int_to_bit(k / 2)));
}
```

&nbsp;

### ASCII-To-Int  

To read the value as an ascii code
```c
#include <stdio.h>

char a = 'a';
int ia = (int)a; 
/* note that the int cast is not necessary -- int ia = a would suffice */
```
To convert the character `'0' -> 0`, `'1' -> 1`
```c
char a = '4';
int ia = a - '0';
/* check here if ia is bounded by 0 and 9 */
```

&nbsp;


---

&nbsp;

## Bit operation functions

&nbsp;


---

&nbsp;

## Masking functions

### Bit masking

... tbd ...

&nbsp;

### Integer masking

To mask single or multiple integers in a integer string you use the modulo operation
```c
int dataString = 12345678
int singleValue = (int)(dataString % 10)         // extract last integer: singleValue = 8
int doubleValue = (int)((dataString/10) % 100)   // 1. division by 10 (= cut last integer)
                                                 // 2. % 100: extract last two integers
                                                 // ==> doubleValue = 67

int firstTwoValues = (int)((dataString)/1000000) % 100)
                                                 // 1. division by 1.000.000 (= cut last 6 integers)
                                                 // 2. % 100: extract last two integers
                                                 // ==> firstTwoValues = 12
```
&nbsp;  

&nbsp;

[Back](../)
