## ⚙️ How it works
Obsidian stores information about last visited Vault inside `obsidian.json` file in default install location `\AppData\Roaming\obsidian\obsidian.json` by adding `"open":true` next to last visided one.

This script removes `"open":true` part forcing Obsidian to open Vault Manager.

`vault-manager.cmd`
```cmd
@echo off
setlocal

:: Define file path
set "input_file=%USERPROFILE%\AppData\Roaming\obsidian\obsidian.json"
set "search_string=,\"open\":true"
set "temp_file=%USERPROFILE%\AppData\Roaming\obsidian\temp.json"

:: Check if the file exists
if not exist "%input_file%" (
    echo File "%input_file%" not found.
    exit /b 1
)

:: Use PowerShell to replace the exact text inside the file
powershell -Command "(Get-Content '%input_file%') -replace '%search_string%', '' | Set-Content '%temp_file%'"

:: Replace original file with the modified one
move /y "%temp_file%" "%input_file%" >nul

:: Start obsidian

powershell -Command "Start-Process '%USERPROFILE%\AppData\Local\Programs\obsidian\Obsidian.exe' -NoNewWindow -PassThru | Out-Null"
```

Because it is nice to not see command prompt pop up for a split second another file is introduced executing script in background.

`start-vault-manager.cmd.vbs`
```vbs
Set objShell = CreateObject("WScript.Shell")
objShell.Run "cmd.exe /c C:\Users\Tomek\AppData\Local\Programs\obsidian\vault-manager.cmd", 0, False
Set objShell = Nothing
```