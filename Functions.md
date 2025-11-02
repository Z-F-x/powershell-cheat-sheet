PowerShell supports functions, and they are a central part of writing reusable scripts or modules.

1. Basic function syntax
function Get-Hello {
    param(
        [string]$Name
    )
    "Hello, $Name!"
}


function Name { ... } → declares the function

param() → defines input parameters

Everything output inside the function is added to the pipeline automatically

Call the function:

Get-Hello -Name "ZFx"
# Output: Hello, ZFx!

2. Functions can have parameters

Named parameters: -Name "Value"

Positional parameters (based on order)

function Add-Numbers {
    param(
        [int]$A,
        [int]$B
    )
    $A + $B
}

Add-Numbers 3 5   # Positional
Add-Numbers -A 3 -B 5  # Named

3. Functions and pipelines

Functions can accept pipeline input using special attributes:

function Show-ProcessName {
    param(
        [Parameter(ValueFromPipeline)]
        [System.Diagnostics.Process]$Process
    )
    $Process.Name
}

Get-Process | Show-ProcessName


ValueFromPipeline allows the function to consume objects from a previous cmdlet.

4. Advanced features

ParameterSets → mutually exclusive sets of parameters

Mandatory parameters → PowerShell prompts if not provided

Return objects → Functions output objects to the pipeline, not just text

Modules → Functions can be grouped into reusable modules

5. Notes for senior-level usage

Functions behave like custom cmdlets.

Always use Verb-Noun naming for clarity.

Avoid Write-Host inside functions if the goal is pipeline output; use Write-Output or just output objects.
