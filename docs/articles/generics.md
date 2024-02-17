---
layout: default
---

[Back](../)

&nbsp;

# Allgemeine To Do's

&nbsp;

> Die hier aufgelisteten *To Do's* sollen über alle Programmiersprachen hinweg Anwendung finden und den Code in allen Belangen besser machen. 

&nbsp;

## Return values

Allgemein ist es in der Programmierwelt üblich, bei einem erfolgreichen Durchlauf durch ein Programm mit

```c
return 0;
```
zurückzukehren.

&nbsp;

### *Return* als Pointer auf einen Fehler

> Jeder andere `return` - Wert (außer *0*) sollte eine Bedeutung haben, d.h. **der int-Wert der zurückgegeben wird, sollte implizit auf den Fehler hindeuten in dessen Zusammenhang er aufgetreten ist.**

&nbsp;

Beispiel:
```c
int function (...) {

    ...
    // Fehler 124: ... ist aufgetreten
    return 124;

    ...
    return 0;

}
```

Auf diese Weise wird in die *Return* - Anweisung gleich eine **Debugger-Funktion** mitimplementiert.  


