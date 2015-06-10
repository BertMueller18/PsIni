﻿# PsIni
## Description  
Work with INI files in PowerShell using hashtables.  

#### Origin
This code was originally a blog post for [Hey Scripting Guy](http://blogs.technet.com/b/heyscriptingguy)
> [Use PowerShell to Work with Any INI File](http://blogs.technet.com/b/heyscriptingguy/archive/2011/08/20/use-powershell-to-work-with-any-ini-file.aspx) 

The individual functions have been published to Miscrosoft's Script Gallery:
* [Get-IniContent](http://gallery.technet.microsoft.com/ea40c1ef-c856-434b-b8fb-ebd7a76e8d91)
* [Out-IniFile](http://gallery.technet.microsoft.com/scriptcenter/7d7c867f-026e-4620-bf32-eca99b4e42f4)

## Examples
Create a Hashtable and save it to C:\settings.ini:

      PS> Import-Module PsIni
      PS> $Category1 = @{"Key1"="Value1";"Key2"="Value2"}
      PS> $Category2 = @{"Key1"="Value1";"Key2"="Value2"}
      PS> $NewINIContent = @{"Category1"=$Category1;"Category2"=$Category2}
      PS> Out-IniFile -InputObject $NewINIContent -FilePath "C:\settings.ini"

Results:

> [Category1]
> Key1=Value1
> Key2=Value2
> 
> [Category2]
> Key1=Value1
> Key2=Value2
 
Returns the key "Key2" of the section "Category2" from the C:\settings.ini file:

      PS>$FileContent = Get-IniContent "C:\settings.ini"
      PS>$FileContent["Category2"]["Key2"]
      Value2

## Contributors
 - Author: [Oliver Lipkau](https://github.com/lipkau) [[blog](http://oliver.lipkau.net/blog/)]
 - Contributor: [Craig Buchanan](https://github.com/craibuc)