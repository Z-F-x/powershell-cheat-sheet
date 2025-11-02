PowerShell has **several types of parameters**, depending on how they behave and what values they accept. Broadly, there are **4 main types**, with a few subcategories:

---

## **1. Named Parameters**

- Standard parameters that take a value.
  
- Always start with `-` followed by **PascalCase**.
  
- Value follows the name (positional or named).
  

`Set-Service -Name "postgresql-x64-18" -StartupType Manual`

- `-Name` → named parameter, value `"postgresql-x64-18"`
  
- `-StartupType` → named parameter, value `Manual`
  

---

## **2. Switch Parameters**

- Boolean flags.
  
- Specified by name only; no value needed.
  
- Default `$false`; specifying sets `$true`.
  

`Get-ChildItem -Recurse -Force`

- `-Recurse` → switch
  
- `-Force` → switch
  
- Can also explicitly assign: `-Recurse:$true`
  

---

## **3. Positional Parameters**

- Passed **without specifying the name**, based on order.
  
- The cmdlet defines which position corresponds to which parameter.
  

`New-Item "C:\Temp\file.txt" File`

- `"C:\Temp\file.txt"` → first positional parameter (`-Path`)
  
- `File` → second positional parameter (`-ItemType`)
  
- You can still use names explicitly for clarity:
  

`New-Item -Path "C:\Temp\file.txt" -ItemType File`

---

## **4. Dynamic / Advanced Parameter Types**

Used mostly in functions or advanced scripts:

| Type | Description |
| --- | --- |
| **Mandatory** | Must be provided, otherwise PowerShell prompts user |
| **ValueFromPipeline** | Accepts input objects from the pipeline |
| **ValueFromPipelineByPropertyName** | Accepts pipeline objects whose property name matches the parameter |
| **ParameterSets** | Allows grouping parameters into mutually exclusive sets |

Example with pipeline input:

`function Show-ProcessName { param( [Parameter(ValueFromPipeline)] [System.Diagnostics.Process]$Process ) $Process.Name } Get-Process | Show-ProcessName`

---

### **Summary Table**

| Type | Syntax | Accepts Value? | Notes |
| --- | --- | --- | --- |
| Named | `-Name Value` | Yes | Most common |
| Switch | `-SwitchName` | No (optional `$true/$false`) | Boolean flags |
| Positional | `Value` | Yes | Order determines mapping |
| Advanced / Pipeline | `[Parameter(ValueFromPipeline)]` | Depends | Used in functions / scripts, supports pipeline binding |
