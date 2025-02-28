# PowerShell

## Create new file in current directory (equivalent to `touch` on gnu/linux systems)
```New-Item -Path "example.txt" -ItemType file```

## Create a new file in current dir, a less verbose way 
```"" | Out-File "example.txt"```

## Check checksum and output it to terminal
```(Get-FileHash "file.zip" -Algorithm SHA512).Hash```

## Remove folder and its content 
```Remove-Item $env:LOCALAPPDATA\someDirectory\ -Recurse -Force```
