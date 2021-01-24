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

First function called is `init_create_window()`
   - Call of subfunction `SpawnWindow(PROJECT_NAME)`.  
      - `SDL_Init(..)` is called to initialize the SDL's subsystems.
      - `DvlIntSetting(<key>, <val>)` is called multiple times with `key -> value` pairs which are set in the "diablo.ini" file.
      - Window setting functions are called (`CalculatePreferdWindowSize`/`AdjustToScreenGeometry`)  
      - In case of *upscaling*, multiple SDL flags are set and SDL functions are called
      - `SDL_CreateWindow(..)` is called and stored in variable `ghMainWnd`
      - SDL object `SDL_DisplayMode` created and SDL functions are called (`SDL_GetDisplayMode(..)` / `SDL_CreateRenderer(..)` / `SDL_CreateTexture(..)` / `SDL_RenderSetIntegerScale(..)` / `SDL_RenderSetLogicalSize(..)` / `SDL_GetWindowSize(..)`)
  - Call of subfunction `dx_init(NULL);`
      - Game window is shown (functions `SDL_RaiseWindow(ghMainWnd)` and `SDL_ShowWindow(ghMainWnd)`)
      - *DirectX* connected functions (`SDL_RenderGetLogicalSize(..)` / `SDL_QueryTexture(..)` / `SDL_CreateRGBSurfaceWithFormat(..)`) are called
      - `palette_init()` is called to initialize the engines color palette.
  - Setting variables *gpBufStart* ("Upper bound of back buffer.") and *gpBufEnd* ("Lower bound of back buffer.")
  - Call of SDL function `SDL_DisableScreenSaver()`.  

Flag *was_window_init* is set to *true*.  

