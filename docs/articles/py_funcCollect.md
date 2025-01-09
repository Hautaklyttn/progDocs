---
layout: default
---

{::options parse_block_html="true" /}  

[Back](../)  

&nbsp;

# Function Collection: Python
---  

&nbsp;

## Conversion functions  

### string-To-Binary

```python
binBitmuster = bin(int(strBitmuster,2))
```

---

&nbsp;

## Bit operation functions

### setBit

```python
def setBit(bitString:int, bit:int):
    return (bitString | (1<<bit))
```

### getBit

```python
def getBit(bitString:int, bit:int):
    return (bitString >> bit) & 1
```

### clearBit

```python
def clearBit(bitString:int, bit:int):
    return (bitString & ~(1<<bit))
```

### bit position in string zurückgeben

```python
def Log2n(n:int):
	if (n > 1):
		return (1 + self.Log2n(n / 2))
	else:
		return 0
```

---

&nbsp;

## Misc functions  

### Quersumme bilden
```python
bitPos = 000100
sum([int(i) for i in str(bitPos)])
```
