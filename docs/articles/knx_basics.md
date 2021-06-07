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
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.2 ... </font>](#ch1-2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">1.2.1 ... </font>](#ch1-2-1)  

### 2. FAQ  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [<font size="-1">2.1 Was ist der Unterschied zwischen **Write** und **Response** in der KNX-Welt? </font>](#ch2-1)  

---  

&nbsp;

# Basics

&nbsp;

<a name="ch1-1"></a>
### 1.1 ...  

&nbsp;

<a name="ch1-2"></a>
### 1.2 ...  

&nbsp;

<a name="ch1-3"></a>
### 1.3 Object - Flags  
> Objekt-Flags definieren das Busverhalten des Objekts, das sie repräsentieren.  

6 verschiedene Objekt-Flags sind definiert:  

• **K**: Kommunikations-Flag  
• **L**: Lese-Flag  
• **Ü**: Übertragen-Flag  
• **S**: Schreiben-Flag  
• **A**: Aktualisieren-Flag  
• **I**: Initialisierungs-Flag  

&nbsp;

**K-Flag**  
Alle anderen Flags sind für dieses Objekt aktiviert.  

**L-Flag**  
Das Gerät wird für dieses Objekt auf ein vom Bus stammendes GroupValueRead-Telegramm reagieren, es sendet also ein GroupValueResponse-Telegramm an den Bus.  

**Ü-Flag**  
Das Gerät überträgt für dieses Objekt jeden aktualisierten Objektwert, es sendet also ein GroupValueWrite-Telegramm an den Bus. Für ein Taster-Objekt bedeutet das beispielsweise, dass eine Wippe, die dieses Objekt darstellt, betätigt wurde. Für ein Taster-Objekt bedeutet das beispielsweise, dass eine Wippe, die dieses Objekt darstellt, betätigt wurde.  

**S-Flag**  
Das Gerät wird für dieses Objekt auf ein GroupValueWrite-Telegramm reagieren, das vom Bus kommt, d. h. es überschreibt den Objektwert. Für einen Schaltaktor bedeutet das beispielsweise, dass ein Relais, das dieses Objekt darstellt, geöffnet oder geschlossen wird.  

**A-Flag**  
Das Gerät wird für dieses Objekt auf ein vom Bus stammendes GroupValueResponse-Telegramm reagieren, es überschreibt also den Objektwert. Für einen Schaltaktor bedeutet das beispielsweise, dass ein Relais, das dieses Objekt darstellt, geöffnet oder geschlossen wird.  

**I-Flag**  
Das Gerät wird für dieses Objekt nach dem Zurücksetzen des Geräts ein GroupValueRead-Telegramm senden. Der Zweck besteht darin, den Objektwert über eine GroupValueResponse abzurufen. Der Grund für das Zurücksetzen des Geräts könnte ein Stromausfall, ein explizites Zurücksetzen des Busses oder eine explizite Anfrage zum Zurücksetzen des Geräts über ein Telegramm sein.  


&nbsp;

&nbsp;

# FAQ

<a name="ch2-1"></a>
### 2.1 Was ist der Unterschied zwischen *Write* und *Response* in der KNX-Welt?  

- **Write** ist das aktive schreiben auf den BUS  
- **Response** ist eine Antwort auf ein Lesetelegramm, dass vom BUS kommt.  

Bei einem **Response** aktualisiert nur das Gerät seinen Status, dass auch das Lesetelegramm abgesetzt hat (abgesehen von den Geräten mit dem gesetzten A-Flag). Bei **Write** wird der Wert von allen mit der GA verbundenen KO's aktualisiert.

&nbsp;

<a name="ch2-2"></a>
### 2.2 ...  

&nbsp;

&nbsp;  

[Back](../)