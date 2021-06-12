---
layout: default
---

[Back](../)  

&nbsp;

# Knx
---  

&nbsp;

### 1. Basics  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.1 ... </font>](#ch1-1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.2 Kommunikationsobjekte </font>](#ch1-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.3 Object - Flags </font>](#ch1-3)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.3.1 ... </font>](#ch1-3-1)  

### 2. FAQ  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">2.1 Was ist der Unterschied zwischen 'Write' und 'Response'? </font>](#ch2-1)  

---  

&nbsp;

# Basics

&nbsp;

<a name="ch1-1"></a>
### 1.1 ...  

&nbsp;

<a name="ch1-2"></a>
### 1.2 Kommunikationsobjekte  
KNX-Geräte tauschen Informationen mit Hilfe ihrer **Kommunikationsobjekte** aus die mit bestimmten **Gruppenadressen** verknüpft sind. Jedes Kommunikationsobjekt steht für eine bestimmte Teilfunktion des Geräts (z.B. Schalten Kanal A). **Alle Kommunikationsobjekte, die mit der gleichen Gruppenadresse verbunden sind, sind miteinander verbunden.** Wenn einer auf diese Gruppenadresse eine Information sendet, bekommen das alle Kommunikationsobjekte entsprechend ihrer Flags mit.  

Jedes Kommunikationsobjekt hat einen bestimmten Datentyp (DPT). Meist geben allerdings die Hersteller nur die Länge in Bit an.
Die Kommunikationsrichtung eines Kommunikationsobjekt kann (hängt vom Applikationprogramm ab) über die sog. Flags (s. *1.3 Object-Flags*) beeinflusst werden.

&nbsp;

<a name="ch1-3"></a>
### 1.3 Object - Flags  

> Objekt-Flags definieren das Busverhalten des Objekts, das sie repräsentieren.  

&nbsp;

6 verschiedene Objekt-Flags sind definiert:  

- **K**: Kommunikations-Flag  
- **L**: Lese-Flag  
- **Ü**: Übertragen-Flag  
- **S**: Schreiben-Flag  
- **A**: Aktualisieren-Flag  
- **I**: Initialisierungs-Flag  

&nbsp;

**K-Flag**  
Alle anderen Flags sind für dieses Objekt aktiviert. Das Kommunikationsobjekt hat normale Verbindung zum Bus.  

**L-Flag** &nbsp;&nbsp; <font color="red">(entscheidend wenn Wert aus Gerät abgerufen wird: GroupValueRead)</font>  
Das Gerät wird für dieses Objekt <u>auf ein vom Bus stammendes GroupValueRead-Telegramm reagieren</u>, es sendet also ein **GroupValueResponse-Telegramm** an den Bus.  
Beispiel ist eine Visualisierung die einen Wert eines Aktors/Sensors auslesen möchte. Dieser Aktor/Sensor muss dann das L-Flag gesetzt haben. Grundsätzlich sollte es in einer GA immer nur ein KO geben, bei dem das L-Flag gesetzt ist!

**Ü-Flag** &nbsp;&nbsp; <font color="red">(entscheidend z.B. bei Schaltern die Wert in GA setzen: GroupValueWrite)</font>  
Das Gerät <u>überträgt für dieses Objekt selbstständig jeden aktualisierten Objektwert</u>, es sendet also ein **GroupValueWrite-Telegramm** an den Bus. Für ein Taster-Objekt bedeutet das beispielsweise, dass eine Wippe, die dieses Objekt darstellt, betätigt wurde.  

**S-Flag**  
Das Gerät wird für dieses Objekt auf ein GroupValueWrite-Telegramm reagieren, das vom Bus kommt, d. h. **es überschreibt seinen Objektwert**.  
Für einen Schaltaktor bedeutet das beispielsweise, dass ein Relais, das dieses Objekt darstellt, geöffnet oder geschlossen wird.  

**A-Flag**  
Das Gerät wird für dieses Objekt auf ein vom Bus stammendes GroupValueResponse-Telegramm reagieren, **es überschreibt also seinen Objektwert**.  
Für einen Schaltaktor bedeutet das beispielsweise, dass ein Relais, das dieses Objekt darstellt, geöffnet oder geschlossen wird.  

**I-Flag**  
Das Gerät wird für dieses Objekt nach dem Zurücksetzen des Geräts ein GroupValueRead-Telegramm senden. Der Zweck besteht darin, den Objektwert über eine GroupValueResponse abzurufen. Der Grund für das Zurücksetzen des Geräts könnte ein Stromausfall, ein explizites Zurücksetzen des Busses oder eine explizite Anfrage zum Zurücksetzen des Geräts über ein Telegramm sein.  

&nbsp;

<u>Beispiel:</u>  
**Die Information Tastendruck soll umgesetzt werden, über den Bus übermittelt, und schließlich das Licht eingeschalten werden.** 

 Zustand oder Informationsgehalt des Taster nennen wir an dieser Stelle <u>Objektwert</u>. Wenn der Nutzer am Taster einen «Ein-» Befehl auslöst, ändert sich der Objektwert auf logisch 1. Diese 1 muss nun weiter übertragen werden, somit muss das Übertragenflag oder **Ü-Flag** gesetzt werden. Weiterhin soll diese Information mit dem Bus kommunizieren. Das Kommunikationsflag oder **K-Flag** muss gesetzt werden. Nun kann die Information mittels Telegramm über den Bus zum Aktor gelangen. Dieser Aktor soll natürlich auch mit dem Bus kommunizieren, deshalb ist auch hier das Kommunikationsflag zu setzen. Es soll aber auch der Objektwert des Aktors geändert werden, denn die Lampe soll einschalten. Um dies zu ermöglichen, muss vom Bus aus gesehen eine Schreiberlaubnis vorhanden sein. Also muss hier noch das Schreiben- oder **S-Flag** gesetzt werden. Zusammenfassend kann man sagen: <font color="red">Bei einem Sensor muss immer das K- und Ü-Flag, bei einem Aktor das K- und S-flag gesetzt werden.</font>  

Das Lesenflag oder **L-Flag** wird benötigt, wenn der Objektwert eines Teilnehmers vom einem anderen Busteilnehmer ausgelesen werden soll. Dies kann beim Speichern von Lichtszenen oder wenn eine Visualisierung sich am Bus aktualisieren soll notwendig werden. Hier ist zu beachten, dass eine Antwort einer solchen Leseanforderung bei manchen (älteren) Busgeräten als Schreibbefehl interpretiert wird. Dies ist nicht schlimm, wenn man die Reihenfolge der Gruppenadressen einhält.

&nbsp;

&nbsp;

# FAQ

<a name="ch2-1"></a>
### 2.1 Was ist der Unterschied zwischen *Write* und *Response*?  

- **Write** ist das aktive schreiben auf den BUS  
- **Response** ist eine Antwort auf ein Lesetelegramm, dass vom BUS kommt.  

Bei einem **Response** aktualisiert nur das Gerät seinen Status, dass auch das Lesetelegramm abgesetzt hat (abgesehen von den Geräten mit dem gesetzten A-Flag). Bei **Write** wird der Wert von allen mit der GA verbundenen KO's aktualisiert.

&nbsp;

<a name="ch2-2"></a>
### 2.2 ...  

&nbsp;

&nbsp;  

[Back](../)
