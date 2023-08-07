# LCD-Simulator
Simuliert ein LCD über Windows-Messages
LCD-Simulator
simuliert ein HD44780 Display. Grösse kann gewählt werden. Fernsteuerbar über Windows-Messages.
Download: LCD-Simulator

![lcd_klein](https://github.com/Chregu73/LCD-Simulator/assets/17860028/0cab75f9-f894-4db7-b549-43ce488df1d8)

Das Programm kann normal mit Doppelklick gestartet werden. Oder in der Kommandozeile mit folgenden Parameter:
1. = Display Typ (0...8) 0 = 16x1, 1 = 16x2, 2 = 16x4, 3 = 20x2, 4 = 20x4, 5 = 24x2, 6 = 24x4, 7 = 40x2, 8 = 40x4
2. = Display Position X-Achse
3. = Display Position Y-Achse
Diese Parameter können auch in der .ini Datei eingestellt werden. Die Position mit Rechtsklick aus dem Programm.
Das Display kann auf dem Screen mit linken Maustaste irgendwo gepackt und bewegt werden.

Ueber Windows-Messages kann der Cursor gesetzt, ins Display geschrieben und Beendet werden:
(Beispielcode für XProfan) Display löschen:
```
Print @SendMessage(lcd_simWin%, $1000, 2, 0)
```

Ein Zeichen (in diesem Fall "T") senden:
```
Print @SendMessage(lcd_simWin%, $1002, 0, @Ord("T"))
```

Display beenden:
```
Print @SendMessage(lcd_simWin%, $1000, 0, 0)
```

Cursor an Position x%, y% setzen:
```
Print @SendMessage(lcd_simWin%, $1001, x%, y%)
```

Beispiel wie das Handle des Display-Fenster ermittelt wird:
```
lcd_sim% = @WinExec("lcd-sim.exe 8 50 600", 5) 'Handle der Anwendung
lcd_simWin% = @GetActiveWindow()
```

Diese Dokumentation ist nicht vollständig. Auch an der Software wird noch gearbeitet.
