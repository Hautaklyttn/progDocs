---
layout: default
---

[Back](../../)

&nbsp;

# Diablo 1 <font size=-1>(1996 - Blizzard North)</font>
---

## Code Walkthrough  

&nbsp;

### **Entry Point** <font size=-1>(Function **WinMain ()**)</font> 

**File**:  
&nbsp;&nbsp;&nbsp;*diablo.cpp*
**Function**:   
*int APIENTRY **WinMain** (HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nCmdShow)*  
&nbsp;
**Purpose**:  
- Checking environment
- Initializes system
- Plays Intro
- Starts Main Menu
- Shut Down
&nbsp;

**Arguments**:
- *hInstance*: A handle to the current instance of the application.
- *hPrevInstance*: Always null
- *lpCmdLine*: The command line for the application
- *nCmdShow*: Initial window state
&nbsp;  

**'APIENTRY'**  
APIENTRY is an alias for *WINAPI*. *WINAPI* itself is a definition for the type of *calling convention* used for windows API calls, the *__stdcall*.  
More info [here](../c_cpp.html#ch1-12).  

&nbsp;

**Walkthrough**  

```c
diablo_reload_process(HINSTANCE hInstance);
```
Defined in *diablo.cpp*.
...tbd...

```c
ShowCursor(FALSE);
```
(Windows function, *winuser.h*)  
Displays or hides the Windows cursor.

```c
srand(GetTickCount());
```
(*stdlib* function)  
*srand* seeds (=initializes) the random number generator. GetTickCount() returns system time with resolution 1 ms.

```c
InitHash();
```
Defined in *encrypt.cpp*.  
Function initializes the hash table (``DWORD hashtable[5][256];``) with predefined numbers.  

```c
fault_get_filter();
```
Defined in *fault.cpp*.
Function returns value of *lpTopLevelExceptionFilter*.

```c
bNoEvent = diablo_get_not_running();
```
Defined in *diablo.cpp*.
Function checks if event "DiabloEvent" (created here by CreateEvent (NULL, FALSE, FALSE, "DiabloEvent") ) was already created, which means the game is already running and returns 0 in case it does already run.

```c
diablo_find_window(GAME_NAME)
```
Defined in *diablo.cpp*.  
*GAME_NAME* is defined in *defs.h*: `#define GAME_NAME "DIABLO"`  
Function checks on operation system level (Windows) if the game is already running.  

```c
diablo_init_screen();
```
Defined in *diablo.cpp*.  
Function centers the mouse cursor and inits values to 0.
Clears the in-game message board.

```c
diablo_parse_flags(lpCmdLine);
```
Defined in *diablo.cpp*.  
Function parses the command line options and sets variables accordingly.

```c
init_create_window(nCmdShow);
```

