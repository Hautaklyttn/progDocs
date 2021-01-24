---
layout: default
---

[Back](../../)

&nbsp;

![d2](../../assets/pics/diablo_inst.png)    

&nbsp;

---  

<font size="-1">&rarr; Code taken from <a href="https://github.com/diasurgical/devilutionX">here.</a></font>  

&nbsp;

## Code Walkthrough  

**File**  
&nbsp;&nbsp;&nbsp;*diablo.cpp*  

**Function**:   
&nbsp;&nbsp;&nbsp; *int DiabloMain(int argc, char \*\*argv)*  

**Walkthrough**  

```c
diablo_parse_flags(argc, argv)
```
- Defined in *diablo.cpp*.  

Function parses possibly given IO Options and sets data or replies accordingly.  

```c
diablo_init()
```
- Defined in *diablo.cpp*.  

  