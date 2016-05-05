# DayZ AHK

This script helps to join server in DayZ.

## Source

```
#NoEnv  ; Recommended for performance and compatibility with future AutoHotkey releases.
SendMode Input  ; Recommended for new scripts due to its superior speed and reliability.
#IfWinActive, DayZ

; Author Brent Plays [checkout my Fb page www.facebook.combrentplays]
F4:: ; Press F4 in game to activate Sprint Mode
	SprintToggle := !SprintToggle
	If (SprintToggle)
	{
		Send, {lshift Down}
		Send, {w Down}
	}
	else
	{
		Send, {lshift up}
		Send, {w up}
	}
Return

; Author Andrii Korzh github.com/korzhyk
F1:: ; Press F1 in server browser with selected server to start "BruteForce"
	JoinToggle := !JoinToggle
	If (JoinToggle)
	{ 
		SetTimer, JoinServer, 1000 ; 1000 in milliseconds is 1 second (every second AHK press Enter)
	}
	else
	{ 
		SetTimer, JoinServer, Off
	}
	JoinServer:
	{
		Send, {Enter}
		WinGetPos, X, Y, Width, Height, DayZ
		Left := Round(Width * 0.5)
		Top := Round(Height * 0.54)
		MouseMove, %Left%, %Top%
		Return
	}
Return
```

## How to use this script

0. Download and install [**AutoHotKey**][AHK]
1. Open Notepad
2. Copy **source** to document
3. And save it with extension **\*.ahk** (DayZ.ahk)

[AHK]: https://autohotkey.com/ "AutoHotKey"
