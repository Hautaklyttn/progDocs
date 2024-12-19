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
self.lastBitmuster = bin(int(self.currBitmuster,2))
```

---

&nbsp;

## Bit operation functions

### setBit

```python
def setBit(self, bit):
    self.resultsInBits = self.resultsInBits | (1<<bit)
```

### getBit

```python
def getBit(self, bit):
    return (self.resultsInBits >> bit) & 1
```

### clearBit

```python
def clearBit(self, bit):
    self.resultsInBits = self.resultsInBits & ~(1<<bit)
```

### bit position in string zurückgeben

```python
def Log2n(self, n):
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
