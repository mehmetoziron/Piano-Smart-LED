# 🎹 Piano LED Project

Dieses Projekt visualisiert MIDI-Daten von einem digitalen Klavier mit modernem USB-B-Anschluss über Java auf dem Computer und steuert adressierbare LEDs über ein Arduino.  

---

## 📌 Projektübersicht

**Verbindung:**  
E-Piano → USB-MIDI → Computer (Java liest MIDI-Daten) → USB → Arduino  

**Funktionsweise:**  
- MIDI-Nachrichten werden am Computer in Java verarbeitet.  
- Noten- und Velocity-Werte werden extrahiert und über USB an das Arduino gesendet.  
- Das Arduino interpretiert die Daten und schaltet die entsprechenden LEDs ein oder aus, inklusive Effekte.  

**Datenfluss:**  
E-Piano: MIDI-MSG (USB) → Computer: Noten- & Velocity-Werte (USB) → Arduino


**Ausgabe:**  
- Arduino steuert LEDs an und aus.  
- Zusätzliche Effekte sind implementiert.  

**Ergebnis:**  
- Die gespielte Musik wird durch Licht visuell dargestellt.  

---

## 🛠 Verwendete Technologien und Bibliotheken

- **Computer & Java** (MIDI-Verarbeitung)  
- **Arduino & C/C++** (LED-Steuerung)  
- **jSerialComm-2.11.0** (Java MIDI-Bibliothek)  
- **Adafruit_NeoPixel** (Arduino LED-Bibliothek)  

---

## 🔌 Hardware-Anforderungen

- Digitales Klavier MIDI USB-Type-B Ausgang ("Casio Celviano AP-260")  
- USB-B zu USB-A/C Kabel  
- Arduino Nano + USB-Kabel  
- WS2812B 5V 176 LEDs (1 m, 144 LEDs/m) + 330 Ω Widerstand  
- Taster + 10 kΩ Widerstand  
- USB-C Stromversorgung (5 V)  

*Hinweis: Taster und Widerstand optional für zusätzliche Effekte.*  

---

## 🚀 Installation & Ausführung

1. `ArduinoController.jar`, `lib`-Ordner und `run.bat` herunterladen  
2. Arduino an die LED-Streifen anschließen und Software hochladen  
   > Piano-Smart-LED/app/MIDI_Led_Piano.ino.with_bootloader.hex ← [HEX-Datei für Arduino](https://github.com/mehmetoziron/Piano-Smart-LED/blob/main/app/MIDI_Led_Piano.ino.with_bootloader.hex)
3. E-Piano mit Computer verbinden  
4. `run.bat` ausführen → COM-Ports werden angezeigt → Arduino COM auswählen  
5. MIDI-Geräte werden angezeigt → E-Piano auswählen  
6. LEDs reagieren auf gespielte Noten; Noten- & Velocity-Werte erscheinen in der Konsole  

---

## 📸 Projektbilder & Schaltplan 

<p align="center">
  <img src="images/LEDs%20Video.gif" height="350">
  <img src="images/connection_data_flow.png" height="350">
</p>

<p align="center">
  <img src="images/Piano_Led_circuit.png" height="350">
  <img src="images/physikalische%20Schaltung.jpg" height="350">
</p>

<p align="center">
  <img src="images/LEDs%20und%20Tasten.jpg" height="350">
  <img src="images/Farboptionen.jpg" height="350">
</p>

---

## 📄 Lizenz / Hinweis

### ⚙️ Arduino-Hex-Datei hochladen

> ⚠️ Hinweis:  
> Der Arduino-Quellcode ist aus urheberrechtlichen Gründen **nicht** im Repository enthalten.  
> Stattdessen steht eine **vorkompilierte HEX-Datei** (`MIDI_Led_Piano.ino.with_bootloader.hex`) zur Verfügung, die direkt auf das Arduino hochgeladen werden kann.

#### Option 1: Arduino IDE
1. Öffne die Arduino IDE.  
2. Wähle dein Board (z. B. *Arduino Nano*) und den entsprechenden COM-Port.  
3. Menü → **Sketch → Mit Programmer hochladen**.  
4. Wähle die Datei `MIDI_Led_Piano.ino.with_bootloader.hex`.  
5. Nach dem Upload startet das Arduino automatisch.

#### Option 2: AVRDude (Kommandozeile)
avrdude -p atmega328p -c arduino -P COM[X] -b 115200 -U flash:w:MIDI_Led_Piano.ino.with_bootloader.hex:i 


## ✨ Entwickler 

**Name:** Mehmet Özdemir 
**GitHub:** [https://github.com/mehmetoziron](https://github.com/mehmetoziron)
