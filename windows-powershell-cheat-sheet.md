# PowerShell

## Execution policies 
If you are seeing errors like this in terminal: 

```
npm i
npm : File C:\nvm4w\nodejs\npm.ps1 cannot be loaded because running scripts is disabled on this system. For more inform
ation, see about_Execution_Policies at https:/go.microsoft.com/fwlink/?LinkID=135170.
At line:1 char:1
+ npm i
+ ~~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess
```

You need to set execution policy to:
```Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser```

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

## Terminate a specific process 
```powershell
taskkill /F /IM processName.exe
```
Note:
`/F`: Force\
`/IM`: Image i.e., a snapshot of the program's executable file in memory.

## Terminate all processes
```PS C:\Users\ZFx\Documents\GitHub\tmp\scraperx-desktop> taskkill /F /IM electron.exe```

Example of expected output:

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

---

### Add Environment Variable to Windows PATH

#### Option 1: Temporarily (for current PowerShell session only)
```powershell
$env:Path += ";C:\msys64\mingw64\bin"
```
> Only lasts until you close the terminal session.

#### Option 2: Permanently (User scope, no admin needed)
```powershell
[Environment]::SetEnvironmentVariable("Path", $env:Path + ";C:\msys64\mingw64\bin", "User")
```
> Adds the path to your user environment variables permanently.

#### Option 3: Permanently (System scope, requires Admin)
```powershell
Start-Process powershell -Verb runAs -ArgumentList {
  $old = [Environment]::GetEnvironmentVariable("Path", "Machine")
  $new = $old + ";C:\msys64\mingw64\bin"
  [Environment]::SetEnvironmentVariable("Path", $new, "Machine")
}
```
> Adds the path to the **system-wide** `Path`. Requires Admin.

#### View All Environment Variables
```powershell
Get-ChildItem Env:
```
> Shows all environment variables in the current session.

---

### Rename file
#### Terse
Rename-Item "old_filename.txt" "new_filename.txt"

#### Verbose:
Rename-Item -Path "old_filename.txt" -NewName "new_filename.txt"

## Output all files of specific extension from current directory and subdirectories (replace *.exe with your file extension).
```
Get-ChildItem -Path . -Recurse -Filter *.exe -File |
    Select-Object -ExpandProperty FullName
```


---
