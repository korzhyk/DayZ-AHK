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
        Send, {LShift Down}
        Send, {W Down}
    }
    else
    {
        Send, {LShift Up}
        Send, {W Up}
    }
Return

; Author Andrii Korzh github.com/korzhyk
F1:: ; Press F1 in server browser with selected server to start "BruteForce"
    JoinToggle := !JoinToggle
    If (JoinToggle)
    {
        SetTimer, JoinServer, 1000 ; 1000 in milliseconds is 1 second
    }
    else
    { 
        SetTimer, JoinServer, Off
    }
    JoinServer:
    {
    	IfWinNotActive, DayZ
    		Return
        WinGetPos, X, Y, Width, Height, DayZ
        MouseMove, Width * 0.5, Height * 0.54
        Send, {Enter}
        Sleep, 100
        Send, {Enter}
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
