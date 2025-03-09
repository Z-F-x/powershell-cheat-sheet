# PowerShell

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
