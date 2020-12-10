---
layout: default
---

[Back](../)

&nbsp;

# Qt und QML
---

&nbsp;

### 1. Basics   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.1 Qt5 / Qt Quick / QML</font>](#ch1-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.1.1 Basic QML concepts</font>](#ch1-1-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.1.2 Properties</font>](#ch1-1-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.1.3 `Signals`</font>](#ch1-1-3)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.2 Application Basics</font>](#ch1-2)  

### 2. How To's   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">2.1 Importing a JS resource from another JS resource</font>](#ch2-1)  

&nbsp;

---  

&nbsp;

# Basics  

> "Qt is a cross platform development framework written in C++."  

- Qt was originally for user interfaces - now for everything (e.g. databases, XML, WebKits, multimedia, networking, OpenGL, scripting, etc.)
- Qt extends C++ with macros and introspection  

  ````c
  foreach (int value, intList) {...}     // macro

  QObject *o = new QPushButton;
  o->metaObject()->classObject();        // introspection (returns "QPushButton")

  connect(button, SIGNAL(clicked()), window, SLOT (close()));    // macro
  ````

&nbsp; 

<a name="ch8-1"></a>
### 1.1 Qt5 / Qt Quick / QML  
**Qt5** is a complete refreshing of the very successful Qt4 release. Qt5 is focusing on the following:  

- Outstanding graphics:  
  Qt Quick 2 is based on OpenGL using a scene graph implementation. The recomposed graphics stack allows a new level of graph effects combined with an ease of use never seen before in this field.
- Developer productivity:  
  QML and JavaScript are the primary means for UI creation. The back-end will be driven by C++. The split between JavaScript and C++ allows a fast iteration for front-end developers concentrating on creating beautiful user interfaces and back-end C++ developers concentrating on stability, performance and extending the runtime.  
- Cross-platform portability:  
  It is now possible to port Qt to a wider range of platforms easier and faster. Qt 5 is structured around the concept of Qt Essentials and Add-ons, which allows OS developer to focus on the essentials modules and leads to a smaller runtime altogether.  

&nbsp; 

**Qt Quick** is the umbrella term for the user interface technology used in Qt 5. Qt Quick itself is a collection of several technologies:  
- QML - Markup language for user interfaces  
- JavaScript - The dynamic scripting language  
- Qt C++ - The highly portable enhanced c++ library  

&nbsp; 

![0x](../assets/pics/qt_quick.png)  

&nbsp; 

Similar to HTML, QML is a markup language. It is composed of tags, called types in Qt Quick, that are enclosed in curly brackets: *Item {}*. It was designed from the ground up for the creation of user interfaces, speed and easier reading for developers. The user interface can be enhanced further using JavaScript code. Qt Quick is easily extendable with your own native functionality using Qt C++. In short, the declarative UI is called the front-end and the native parts are called the back-end. This allows you to separate the computing intensive and native operation of your application from the user interface part.  

In a typical project, the front-end is developed in QML/JavaScript. The back-end code, which interfaces with the system and does the heavy lifting, is developed using Qt C++. This allows a natural split between the more design-oriented developers and the functional developers.  

&nbsp; 

The **Qt Essentials modules** are mandatory for any Qt-enabled platform. They offer the foundation to develop modern Qt 5 Applications using Qt Quick 2.  

|Module|Description|
|:---|:---|
|Qt Core|Core non-graphical classes used by other modules.|
|Qt GUI|Base classes for graphical user interface (GUI) components. Includes OpenGL.|
|Qt Multimedia|Classes for audio, video, radio and camera functionality.|
|Qt Multimedia Widgets|Widget-based classes for implementing multimedia functionality.|
|Qt Network|Classes to make network programming easier and more portable.|
|Qt QML|Classes for QML and JavaScript languages.|
|Qt Quick|A declarative framework for building highly dynamic applications with custom user interfaces.|
|Qt Quick Controls 2|Provides lightweight QML types for creating performant user interfaces for desktop, embedded, and mobile devices. These types employ a simple styling architecture and are very efficient.|
|Qt Quick Dialogs|Types for creating and interacting with system dialogs from a Qt Quick application.|
|Qt Quick Layouts|Layouts are items that are used to arrange Qt Quick 2 based items in the user interface.|
|Qt Quick Test|A unit test framework for QML applications, where the test cases are written as JavaScript functions.|
|Qt SQL|Classes for database integration using SQL.|
|Qt Test|Classes for unit testing Qt applications and libraries.|
|Qt Widgets|Classes to extend Qt GUI with C++ widgets.|

&nbsp; 

![0c](../assets/pics/qt_core.png)  

&nbsp; 

<a name="ch1-1-1"></a>
#### 1.1.1 Basic QML Concepts  

```js
Image {
    id: root
    ...
    Image {
        id: pole
        anchors.horizontalCenter: parent.horizontalCenter
        anchors.bottom: parent.bottom
        source: "images/pole.png"
    }

    Image {
        id: wheel
        anchors.centerIn: parent
        source: "images/pinwheel.png"
    }
    ...
}
```

Placing an image as a child type of our root type (the *Image*) illustrates an important concept of a declarative language. You describe the visual appearance of the user interface in the order of layers and grouping, where the topmost layer (our background image) is drawn first and the child layers are drawn on top of it in the local coordinate system of the containing type.  

```
Image {
    id: root
    ...
    MouseArea {
        anchors.fill: parent
        onClicked: wheel.rotation += 90
    }
    ...
}
```

The mouse area emits signals when the user clicks inside the area it covers. You can connect to this signal by overriding the *onClicked* function.  

This technique works for every signal, with the naming convention being  
```js
on + SignalName
```


Also, all properties emit a signal when their value changes. For these signals, the naming convention is:
```js
on + PropertyName + Changed
```

For example, if a width property is changed, you can observe it with ``onWidthChanged: print(width)``.  

&nbsp; 

<a name="ch1-1-2"></a>
#### 1.1.2 Properties  
Elements are declared by using their element name but are defined by using their properties or by creating custom properties. A property is a simple key-value pair, e.g. *width : 100*, *text: 'Greetings'*, *color: '#FF0000'*. A property has a well-defined type and can have an initial value.  

```js
Text {
    // (1) identifier
    id: thisLabel

    // (2) set x- and y-position
    x: 24; y: 16

    // (3) bind height to 2 * width
    height: 2 * width

    // (4) custom property
    property int times: 24

    // (5) property alias
    property alias anotherTimes: thisLabel.times

    // (6) set text appended by value
    text: "Greetings " + times

    // (7) font is a grouped property
    font.family: "Ubuntu"
    font.pixelSize: 24

    // (8) KeyNavigation is an attached property
    KeyNavigation.tab: otherLabel

    // (9) signal handler for property changes
    onHeightChanged: console.log('height:', height)

    // focus is need to receive key events
    focus: true

    // change color based on focus value
    color: focus?"red":"black"
}
```

Let’s go through the different features of properties:  

1. *id* is a very special property-like value, it is used to reference elements inside a QML file (called “document” in QML). The *id* is not a string type but rather an identifier and part of the QML syntax. An *id* needs to be unique inside a document and it can’t be reset to a different value, nor may it be queried. (It behaves much like a reference in the C++ world.)  
&nbsp; 
2. A property can be set to a value, depending on its type. If no value is given for a property, an initial value will be chosen. You need to consult the documentation of the particular element for more information about the initial value of a property.  
&nbsp; 
3. A property can depend on one or many other properties. This is called binding. A bound property is updated when its dependent properties change. It works like a contract, in this case, the *height* should always be two times the *width*.  
&nbsp; 
4. Adding own properties to an element is done using the *property* qualifier followed by the type, the name and the optional initial value (*property \<type\> \<name\> : \<value\>*). If no initial value is given a system initial value is chosen.  
&nbsp; 
5. Another important way of declaring properties is using the *alias* keyword (*property alias \<name\>: \<reference\>*). The *alias* keyword allows us to forward a property of an object or an object itself from within the type to an outer scope. We will use this technique later when defining components to export the inner properties or element ids to the root level. A property alias does not need a type, it uses the type of the referenced property or object.  
&nbsp; 
6. The *text* property depends on the custom property *times* of type int. The *int* based value is automatically converted to a *string* type. The expression itself is another example of binding and results in the text being updated every time the *times* property changes.  
&nbsp; 
7. Some properties are grouped properties. This feature is used when a property is more structured and related properties should be grouped together. Another way of writing grouped properties is *font { family: "Ubuntu"; pixelSize: 24 }*.  
&nbsp; 
8. Some properties are attached to the element itself. This is done for global relevant elements which appear only once in the application (e.g. keyboard input). The writing is *\<Element\>.\<property\>: \<value\>*.  
&nbsp; 
9. For every property, you can provide a signal handler. This handler is called after the property changes. For example, here we want to be notified whenever the height changes and use the built-in console to log a message to the system.  
&nbsp; 

You can also declare one property to be the default property if no property name is given by prepending the property declaration with the *default* keyword. This is used for example when you add child elements, the child elements are added automatically to the default property *children* of type list if they are visible elements.  

&nbsp; 

**Property Aliases**  
Unlike a property definition, which allocates a new, unique storage space for the property, a property alias connects the newly declared property, called the aliasing property as a direct reference to an existing property, the aliased property. Read or write operations on the aliasing property results in a read or write operations on the aliased property, respectively.  

A property alias declaration is similar to an ordinary property definition:  

``[default] property alias <name>: <alias reference>``  

As the aliasing property has the same type as the aliased property, an explicit type is omitted, and the special *alias* keyword is before the property name. Instead of a default value, a property alias has a compulsory alias reference. Accessing the aliasing property is similar to accessing a regular property. In addition, the optional default keyword indicates that the aliasing property is a default property.  

```js
property alias buttonLabel: label.text
Text {
    id: label
    text: "empty label"
}
```  

When importing the component as a *Button*, the *buttonlabel* is directly accessible through the *label* property.  

```js
Button {
    id: textbutton
    buttonLabel: "Click Me!"
}
```  

In addition, the *id* property may also be aliased and referred outside the component.  

```js
Rectangle {
    property alias buttonImage: image

    Image {id: image}
}
```  

The *imagebutton* component has the ability to modify the child Image object and its properties.

```js
Button {
    id: imagebutton
    buttonImage.source: "http://qt.nokia.com/logo.png"
    buttonLabel: buttonImage.source
}
```  

&nbsp; 

> Using aliases, properties may be exposed to the top level component. Exposing properties to the top-level component allows components to have interfaces similar to Qt widgets.  

> (!) Aliases are only activated once the component completes its initialization. An error is generated when an uninitialized alias is referenced. Likewise, aliasing an aliasing property will also result in an error.

&nbsp; 

<a name="ch1-1-3"></a>
#### 1.1.3 `Signals`  

1. **Adding Signals to Custom QML Types**  

    Signals can be added to custom QML types through the *signal* keyword.  
    The syntax for defining a new signal is:

    ```js
    signal <name> [([<type> <parameter name>[, ...]])]
    ```

    A signal is emitted by invoking the signal as a method.  

    For example, say the code below is defined in a file named *xy.qml*. The root *Rectangle* object has an *activated* signal. When the child *MouseArea* is clicked, it emits the parent's *activated* signal with the coordinates of the mouse click:

    ```js
    // Xy.qml
    Rectangle {
        id: root

        signal activated(real xPosition, real yPosition)

        property int side: 100
        width: side; height: side

        MouseArea {
            anchors.fill: parent
            onPressed: root.activated(mouse.x, mouse.y)
        }
    }
    ```

    Now any objects of the *Xy* can connect to the *activated* signal using an *onActivated* signal handler:  

    ```js
    // myapplication.qml
    Xy {
        onActivated: console.log("Activated at " + xPosition + "," + yPosition)
    }
    ```
    &nbsp;  
2. **Connecting Signals to Methods and Signals**  
    Signal objects have a *connect()* method to connect a signal either to a method or another signal. When a signal is connected to a method, the method is automatically invoked whenever the signal is emitted. This mechanism enables a signal to be received by a method instead of a signal handler.  
    &nbsp;
    Below, the *messageReceived* signal is connected to three methods using the *connect()* method:  
    ```js
    Rectangle {
        id: relay

        signal messageReceived(string person, string notice)

        Component.onCompleted: {
            relay.messageReceived.connect(sendToPost)
            relay.messageReceived.connect(sendToTelegraph)
            relay.messageReceived.connect(sendToEmail)
            relay.messageReceived("Tom", "Happy Birthday")
        }

        function sendToPost(person, notice) {
            console.log("Sending to post: " + person + ", " + notice)
        }
        function sendToTelegraph(person, notice) {
            console.log("Sending to telegraph: " + person + ", " + notice)
        }
        function sendToEmail(person, notice) {
            console.log("Sending to email: " + person + ", " + notice)
        }
    }
    ```  
    In many cases it is sufficient to receive signals through signal handlers rather than using the *connect()* function. However, using the *connect* method allows a signal to be received by multiple methods as shown above, which would not be possible with signal handlers as they must be uniquely named. Also, the *connect* method is useful when connecting signals to dynamically created objects.  
    

&nbsp; 

<a name="ch1-2"></a>
### 1.2 Application Basics  
 
````c
#include <QApplication>
#include <QLabel>

int main (int argc, char **argv) {
  QApplication app(argc, argv);
  QLabel l("Hello World!");
  l.show();
  return app.exec();
}
````

**QApplication**  
Jede Applikation enthält genau eine (!) Instanz dieser Klasse. Sie hält das Ganze zusammen und bewerkstelligt die Kommunikation zwischen Benutzer und den Objekten. Wichtig: am Ende der Main-Methode der *exec()* - Aufruf.  

**QObject**  
QObject ist die Basisklasse von nahezu allen QT-Klassen und allen Widgets. Sie enthält viele der Machanismen die Qt ausmachen, z.b. Events, *Signals&Slots* oder Speichermanagement.  

**QWidget**  
abgeleitet von der 'Urklasse' *QObject*, stellt eine Instanz der Klasse QWidget ein grafisches Element dar. Die Klasse Widget bringt viele der Methoden mit, um das Aussehen, Größe, Position auf dem Bildschirm, etc. zu verändern. Mit *show()* wird das Widget angezeigt, mit *hide()* versteckt. Jedes Widget wird innerhalb dessen Vater-Widgets dargestellt.  

&nbsp;

**[Meta Data]**  
- Qt implements introspection in C++  
    - every QObject has a meta object
    - the meta object knows about  
        - class name (QObject::className)
        - inheritance (QObject::inherits)
        - properties
        - signals and slots
        - general information (QObject::classInfo)
- The meta data is gathered at compile time by the *meta object compiler* (moc)
- The *moc* harvests data from the header  

&nbsp;

![emu](../assets/pics/mocs_qt.png)  

&nbsp;

- What does *moc* look for?  

&nbsp;

&nbsp;


# How To's

<a name="ch2-1"></a>
### 2.1 Importing a JS resource from another JS resource  

1. A JavaScript resource may import another in the following way:  
    ```js
    .import "filename.js as <qualifier>"
    ``` 
    (!) Dieser Weg ist nicht praktikabel, wenn zwischen den Files wechselseitige Abhängigkeiten bestehen (z.B. Methodenaufrufe), da die Files sich gegenseitig importieren müssten (&rarr; Schleife!).  
    &nbsp;  
2. It is possible to make functions available in the importing context (in the QML file) without needing to qualify them. In this circumstance the `Qt.include(<js_file>)` function may be used to include one JavaScript file from another. This copies all functions from the other file into the current files namespace, but ignores all *pragmas* and *imports* defined in that file.  
    ```js
    Qt.include(<js_file>)
    ```

&nbsp;  

[Back](../)
