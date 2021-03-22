---
layout: default
---

{::options parse_block_html="true" /}  

[Back](../)  

&nbsp;

# C Function Collection
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
	const char binary[16][5] = {"0000", "0001", "0010", "0011", "0100", "0101", "0110", "0111", "1000", \
	"1001", "1010", "1011", "1100", "1101", "1110", "1111"};

	char single[2];
	memset(single, '\0', sizeof(single));

    for (int j=0; j<strlen(hex); j++) {
        single[0] = hex[j];
		strcat(binContainer, binary[Hex2Dec(single)]);
    }
}
```

&nbsp;

### Binary-To-X

```c
#include <stdlib.h>

static long Bin2Dec(char* binary) {
    long decimal = strtol(binary, NULL, 2);
    return decimal;
}
```

```c
// 'hexContainer': "char container[16]; memset(container, '\0', sizeof(container));"
static void Bin2Hex(char* binary, char* hexContainer) {
	long decimal = Bin2Dec(binary);
	Dec2Hex(decimal, hexContainer);
}
```

&nbsp;

### Decimal-To-X  

```c
#include <stdio.h>

// 'hexContainer': "char container[16]; memset(container, '\0', sizeof(container));"
static void Dec2Hex(int decimal, char* hexContainer) {
    sprintf(hexContainer, "%x", decimal);
}
```

&nbsp;

---

&nbsp;

## Bit operation functions


&nbsp;  

&nbsp;

[Back](../)