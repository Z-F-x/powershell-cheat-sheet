# PowerShell

## Powershells dotfile location
`C:\Users\YourUserName\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1`

## I think it's different from
$HOME\Documents\PowerShell\Microsoft.PowerShell_profile.ps1

## Create new file in current directory (equivalent to `touch` on gnu/linux systems)

`New-Item -Path "example.txt" -ItemType file`

## Create a new file in current dir, a less verbose way

`"" | Out-File "example.txt"`

## Delete a file in current directory

`Remove-Item exampleFileName.txt`

## Check checksum and output it to terminal

`(Get-FileHash "file.zip" -Algorithm SHA512).Hash`

## Remove folder and its content

`Remove-Item $env:LOCALAPPDATA\someDirectory\ -Recurse -Force`

## Copy all files and folder with their content to another directory

`Copy-Item -Path "C:\Source\*" -Destination "C:\Destination" -Recurse`

## Create a symbolic link to an `.exe` file

### Run cmd as administrator:

#### This will create for a specific folder only

`mklink C:\path\to\folderYouWantTheProgramToRunIn\executableProgram.exe C:\path\to\your\executableProgram.exe`

#### Thiis will create it as a global available command

`mklink C:\Windows\executableProgram.exe C:\path\to\your\executableProgram.exe`

## Remove a folder with it's content

`Remove-Item -Path \path\to\folder -Recurse -Force`

## Delete file

`Remove-Item -Path \path\to\file.ext`

### Aliases for deleting file

     ```rm -Path "C:\path\to\file.txt"```
     ```del "C:\path\to\file.txt"```

## List all hardware connected disks

`Get-Disk`

## Inspect partitions on the disks

`Get-Partition -DiskNumber 0`
`Get-Partition -DiskNumber 1`

### See flag options for Get-Partition:

`Get-Help Get-Partition -Full`

## Terminate all processes
PS C:\Users\ZFx\Documents\GitHub\tmp\scraperx-desktop> taskkill /F /IM electron.exe
```
SUCCESS: The process "electron.exe" with PID 17400 has been terminated.
SUCCESS: The process "electron.exe" with PID 29628 has been terminated.
SUCCESS: The process "electron.exe" with PID 29252 has been terminated.
SUCCESS: The process "electron.exe" with PID 28688 has been terminated.
SUCCESS: The process "electron.exe" with PID 29672 has been terminated.
```


## Get list of process of specific type
```Get-Process node```

### Kill the task based on pid
```Stop-Process -Id <PID>```


### Stop all processes of type
```Get-Process node | Stop-Process```

### Confirm before stopping the process:

```Get-Process node | ForEach-Object { $_; Read-Host "Stop this process? (Y/N)" | Where-Object { $_ -eq 'Y' } | ForEach-Object { $_.Kill() } }```

