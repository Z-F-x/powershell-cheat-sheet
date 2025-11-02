1. **Input/Output**
  
  - `Out-File`, `Export-CSV`, `ConvertTo-Json`, `Set-Content`
    
  - Handling streams (standard, error, verbose, debug)
    

---

## **Part IV — Control Flow and Logic**

1. **Conditionals**
  
  - `if`, `elseif`, `else`
    
  - `switch` (with regex and script blocks)
    
2. **Loops**
  
  - `for`, `foreach`, `while`, `do`
    
  - `ForEach-Object` vs `foreach` statement
    
  - Loop control: `break`, `continue`
    
3. **Functions**
  
  - Defining, calling, and scoping
    
  - Parameter declarations and attributes (`[Parameter()]`)
    
  - Pipeline input handling
    
4. **Error Handling**
  
  - `try` / `catch` / `finally`
    
  - `$Error`, `$?`, `$LASTEXITCODE`
    
  - `throw`, `Write-Error`, and error records
    

---

## **Part V — Data Manipulation**

1. **Objects and Properties**
  
  - Inspecting objects (`Get-Member`)
    
  - Accessing and modifying properties
    
  - Calculated properties (`Select-Object @{Name=...; Expression=...}`)
    
2. **Arrays and Collections**
  
  - Indexing, slicing, and filtering
    
  - `foreach` enumeration
    
  - Sorting and grouping
    
3. **Text Processing**
  
  - Regular expressions (`-match`, `[regex]::Matches()`)
    
  - String formatting (`-f`, interpolation)
    
  - Parsing structured data (CSV, JSON, XML)
    

---

## **Part VI — Files, Registry, and System Interaction**

1. **File System**
  
  - Providers and drives (`Get-PSDrive`)
    
  - Path manipulation (`Join-Path`, `Split-Path`)
    
  - File I/O (`Get-Content`, `Set-Content`, `Out-File`)
    
2. **Registry Access**
  
  - Navigating `HKLM:` and `HKCU:` drives
    
  - Reading/writing registry values
    
3. **Processes and Services**
  
  - `Get-Process`, `Stop-Process`, `Start-Service`
    
  - `Invoke-Command` for remote process control
    

---

## **Part VII — Modules and Scripting Structure**

1. **Scripts**
  
  - `.ps1` files and execution policy
    
  - Script parameters (`param()`)
    
  - Returning values and exit codes
    
2. **Modules**
  
  - Creating and importing modules (`.psm1`, manifest)
    
  - Namespaces and export control (`Export-ModuleMember`)
    
3. **Profiles and Startup Scripts**
  
  - `$PROFILE` files
    
  - Customizing the PowerShell environment
    

---

## **Part VIII — Object-Oriented PowerShell**

1. **Classes**
  
  - Defining classes and constructors
    
  - Inheritance and methods
    
  - Working with .NET types and assemblies
    
2. **PSCustomObject**
  
  - Creating lightweight data objects
    
  - Use in structured output (e.g., CSV/JSON pipelines)
    

---

## **Part IX — Advanced Features**

1. **Scripting Best Practices**
  
  - Comment-based help (`<# .SYNOPSIS ... #>`)
    
  - Verb-Noun naming, readability
    
  - Avoiding unintentional global state
    
2. **Regular Expressions and Parsing**
  
  - Capture groups and named matches
    
  - Text transformation
    
3. **Jobs and Parallelism**
  
  - `Start-Job`, `Receive-Job`, `Wait-Job`
    
  - Runspaces and `ForEach-Object -Parallel`
    
4. **Remoting and Security**
  
  - `Enter-PSSession`, `Invoke-Command`
    
  - Execution policies and signing
    
  - Credential handling (`Get-Credential`, `SecureString`)
    

---

## **Part X — Ecosystem and Integration**

1. **.NET Integration**
  
  - Accessing .NET classes directly
    
  - Invoking static methods
    
  - Working with assemblies (`Add-Type`)
    
2. **Interfacing with External Tools**
  
  - Handling text-based CLI output
    
  - Invoking executables and parsing results
    
3. **Automation Targets**
  
  - Windows API, COM objects
    
  - WMI / CIM for system management
    
  - REST APIs (`Invoke-RestMethod`)
    

---

## **Part XI — Testing, Debugging, and Maintenance**

1. **Debugging**
  
  - Breakpoints, `Set-PSBreakpoint`
    
  - `Write-Debug`, `Write-Verbose`
    
  - Interactive debugging in ISE or VSCode
    
2. **Testing**
  
  - Pester framework basics
    
  - Writing unit and integration tests
    
3. **Logging and Monitoring**
  
  - Logging strategies
    
  - Event logs and transcript files
    

---

## **Part XII — Patterns and Design in PowerShell**

1. **Pipeline-Oriented Design**
  
  - Functions as producers and consumers
    
  - Stream-safe operations
    
2. **Reusable Tools**
  
  - Modular structure, configuration separation
    
  - Output standardization (objects, not text)
    
3. **Idioms and Anti-patterns**
  
  - Avoiding text parsing for structured data
    
  - Avoiding unnecessary `Write-Host`
    

---

## **Part XIII — Appendix**

1. **Cheat Sheets**
  
  - Common cmdlets grouped by purpose
    
  - Operators summary
    
  - Type accelerators reference
    
2. **Built-in Variables**
  
  - `$PSVersionTable`, `$HOME`, `$PWD`, etc.
3. **Command Reference**
  
  - Core modules (`Microsoft.PowerShell.Management`, `Utility`, `Security`)
4. **PowerShell Profiles by Use Case**
  
  - Automation
    
  - System administration
    
  - Development
