---
layout: default
---

{::options parse_block_html="true" /}  

[Back](../)  

&nbsp;

# Best To Do's in C
---  

&nbsp;

> Die hier aufgelisteten *To Do's* sollen deinen C-Code in allen Belangen besser machen. 

&nbsp;

## Anwendung des *Object Pattern*  

### Eigenschaften
- **Gruppierung von Daten** - alle Variablen werden in `structs` (*Objekte*) gruppiert. Es werden niemals globale Variablen angelegt und damit auch nie auf sie zugegriffen.
- **Die Daten werden zur Verarbeitung in `structs` als Parameter an Funktionen übergeben.** Dabei wird innerhalb der Funktion der Parameter `self` verwendet um auf die Daten zuzugreifen.
- **Funktionen haben keine statischen Daten**: Alle Daten sind Teil des Objekts (unserem *struct*), an dem gearbeitet wird.
- **Datenverarbeitung geschieht entlang eines Aufrufpfads**, d.h. Funktionen werden immer mit dem *struct* als Parameter aufgerufen, was dazu führt, dass ein klarer Pfad der Daten verfolgt werden kann.

&nbsp;

### Use Cases  

**Allgemein immer anwenden**: Das *Object Pattern* sollte immer angewendet werden, da es
- Kapselung von Daten fördert (Objektorientierung in C)
- Lesbarkeit und Verständlichkeit des Codes erhöht
- Modularität fördert

**Singletons:** Das *Object Pattern* ist auch die primäre Möglichkeit, ``Singletons`` zu implementieren. Da alle Daten, die zuvor statisch innerhalb der Singleton-Implementierung definiert wurden, jetzt in einem Singleton-Objekt platziert werden können und alle privaten Singleton-Objektmethoden für die Bearbeitung dieses Objekts eingerichtet werden können.

**Abstract interfaces**: Das *Object Pattern* ist eine Schlüsselkomponente von `abstract interfaces`.

**Multithread-Design**: Das *Object Pattern* ist für das Multithread-Design von wesentlicher Bedeutung, da es bei der Thread-Synchronisierung um das „Sperren von Daten – nicht um Code“ geht. Objekte sind fundamental für die Gruppierung von Daten und damit die Möglichkeit ein klares *Lock* für eine Gruppe von Variablen zu erlangen für die der Zugriff synchronisiert werden muss.

&nbsp;

### Implementierung  

File: **my_object.h** (Definition)
```c
struct my_object {
  uint32_t variable;
  uint32_t flags;
}

int my_object_init (struct my_object *self);
int my_object_deinit (struct my_object *self);
```
Jedes Objekt (=struct) erhält eine `init`/`deinit`-Funktion. Analog zum Konstruktor in OO-Sprachen.

&nbsp;

File: **my_object.c** (Implementierung)
```c
#include "my_object.h"

int my_object_init (struct my_object *self) {
  memset(self, 0, sizeof(*self));
}

int my_object_deinit (struct my_object *self){
  //cleanup
}

```

&nbsp;

File: **application.c** (Benutzung)
```c
#include "my_object.h"

struct application {
  struct my_object obj;
}

int application_init (struct application *self) {
  my_object_init(&self->obj);
}
```

&nbsp;

### Regeln  

- **Funktionen *wirken* auf Objekte**: Jede Funktion muss auf ein Objekt wirken, auf das ein „self“-Argument verweist. Alle zusätzlichen Parameter, die an die Funktion übergeben werden, dienen dazu, das Verhalten zu ändern, das auf das „self“-Objekt angewendet wird. Das „self“-Objekt ist das primäre Objekt, das geändert wird, und auch der Ort, an dem die Ergebnisse gesammelt werden. Alle Ausgabevariablen können natürlich auch als Argumente übergeben werden, und solche Daten gelten als aus dem Objekt „exportiert“ und fallen in die Verantwortung des Aufrufers, sobald die Methode zurückkehrt.  
- **Funktionen werden mit dem Objektnamen als Präfix versehen**: Jede Funktion, die auf ein Objekt einwirkt, sollte mit dem Typnamen dieses Objekts als Präfix versehen und in einer Datei mit demselben Namen abgelegt werden. Dies dient einer übersichtlichen Organisation und Übersichtlichkeit beim Lesen des Codes.  
- **Kein globaler Zugriff auf statische Daten**: Es dürfen keine globalen und statischen Daten verwendet werden – alle verwendeten Daten müssen aus den Argumenten stammen (d. h. Sie können innerhalb der Funktion nicht auf statische Daten zugreifen, aber die Daten, die Sie an die Funktion übergeben, können natürlich statisch sein – es gibt nur Einschränkungen hinsichtlich dessen, worauf Sie innerhalb der Funktion zugreifen können).

&nbsp;

### *extern* == Bad code

Bad header file
```c
...
extern uint32_t value;
...
```

Bad .c file
```c
#include <bad_header.h>

void your_method(struct your *self) {
  value = 123;
}
```

> *extern* soweit wie möglich vermeiden! Stattdessen das *Object Pattern* verwenden.  

&nbsp;

***  

## ...