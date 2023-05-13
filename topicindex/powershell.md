# create directory C:\knowledge\github\powershell
New-Item -Path 'C:\knowledge\github\powershell\TestFolder' -ItemType Directory
# Create file
New-Item -Path 'C:\knowledge\github\powershell\TestFolder\testFile.txt' -ItemType File
# ::Grant Read and Execute Access of a specific file
ICACLS "C:\knowledge\github\powershell\TestFolder\testFile.txt" /grant:r "users:(RX)" /C
Set-Content -Path 'C:\knowledge\github\powershell\TestFolder\testFile.txt' 'Welcome to TutorialsPoint'
# Copy folder or Copy-Item 'D:\temp\Test Folder' -Destination 'D:\temp\Test Folder1'
Copy-Item 'C:\knowledge\github\powershell\TestFolder' 'C:\knowledge\github\powershell\DeleteTestFolder'
#  copy file
Copy-Item 'C:\knowledge\github\powershell\TestFolder\testFile.txt' 'C:\knowledge\github\powershell\DeleteTestFolder\testFile.txt'
# Copy-Item -Filter *.txt -Path 'D:\temp\Test Folder' -Recurse -Destination 'D:\temp\Test Folder1'
# Delete file
Remove-Item 'C:\knowledge\github\powershell\DeleteTestFolder\testFile.txt'
# delete folder
Remove-Item 'C:\knowledge\github\powershell\DeleteTestFolder' -Recurse
#Remove-Item 'C:\knowledge\github\powershell\TestFolder' -Recurse
# Move folder
Move-Item C:\knowledge\github\powershell\TestFolder C:\knowledge\github\powershell\TestFolder2
# Movie file Move-Item D:\temp\Test\Test.txt D:\temp\Test1
# rename folder
Rename-Item "C:\knowledge\github\powershell\TestFolder2" "TestFolder"
## rename file
Rename-Item C:\knowledge\github\powershell\TestFolder\testFile.txt testFile2.txt
# retrieving content
Get-Content C:\knowledge\github\powershell\TestFolder\testFile2.txt
# length of the file
(Get-Content C:\knowledge\github\powershell\TestFolder\testFile2.txt).length
# Folder existence
Test-Path D:\temp\test
# file existence
Test-Path D:\temp\test\test.txt
#Delete test data
Remove-Item 'C:\knowledge\github\powershell\TestFolder' -Recurse





# date commands
get-date
# set-date -Date (Get-Date).AddDays(1)
set-date -Date (Get-Date).AddDays(1)
# get date in different format
set-date -Date (Get-Date).AddDays(1)
# Get system time
Get-Date -DisplayHint Time
$timeToAdd = New-TimeSpan -Minutes -60
set-date -adjust $timeToAdd




#Format value
#Matches exact characters anywhere in the original value.
"book" -match "oo"

#Format   .
#Logic    Matches any single character.
"copy" -match "c..y"

#Format   [value]
#Logic    Matches at least one of the characters in the brackets.
"big" -match "b[iou]g"

#Format   [range]
#Logic    Matches at least one of the characters within the range. The use
#         of a hyphen (-) allows you to specify an adjacent character.
"and" -match "[a-e]nd"

#Format   [^]
#Logic    Matches any characters except those in brackets.
"and" -match "[^brt]nd"

#Format   ^
#Logic    Matches the beginning characters.
"book" -match "^bo"

#Format   $
#Logic    Matches the end characters.
"book" -match "ok$"

#Format   *
#Logic    Matches any instances of the preceding character.
"baggy" -match "g*"

#Format   ?
#Logic    Matches zero or one instance of the preceding character.
"baggy" -match "g?"

##
##Format:  \p{name}
#Logic:   Matches any character in the named character class specified by
#         {name}. Supported names are Unicode groups and block ranges such
#         as Ll, Nd, Z, IsGreek, and IsBoxDrawing.
 "abcd defg" -match "\p{Ll}+"

#Format:  \P{name}
#Logic:   Matches text not included in the groups and block ranges specified
#         in {name}.
 1234 -match "\P{Ll}+"

#Format:  \w
#Logic:   Matches any word character. Equivalent to the Unicode character
#         categories [\p{Ll}\p{Lu}\p{Lt}\p{Lo}\p{Nd}\p{Pc}]. If ECMAScript-
#         compliant behavior is specified with the ECMAScript option, \w is
#         equivalent to [a-zA-Z_0-9].
 "abcd defg" -match "\w+" #(this matches abcd)

#Format:  \W
#Logic:   Matches any nonword character. Equivalent to the Unicode categories
#         [^\p{Ll}\p{Lu}\p{Lt}\p{Lo}\p{Nd}\p{Pc}].
 "abcd defg" -match "\W+" #(this matches the space)

#Format:  \s
#Logic:   Matches any white-space character. Equivalent to the Unicode
#         character categories [\f\n\r\t\v\x85\p{Z}].
 "abcd defg" -match "\s+"

#Format:  \S
#Logic:   Matches any non-white-space character. Equivalent to the Unicode
#         character categories [^\f\n\r\t\v\x85\p{Z}].
 "abcd defg" -match "\S+"

#Format:  \d
#Logic:   Matches any decimal digit. Equivalent to \p{Nd} for Unicode and
#         [0-9] for non-Unicode behavior.
 12345 -match "\d+"

#Format:  \D
#Logic:   Matches any nondigit. Equivalent to \P{Nd} for Unicode and [^0-9]
#         for non-Unicode behavior.
 "abcd" -match "\D+"



##
#Format:  *
#Logic    Specifies zero or more matches; for example, \wor (abc). Equivalent
#         to {0,}.
 "abc" -match "\w*"

#Format:  +
#Logic:   Matches repeating instances of the preceding characters.
 "xyxyxy" -match "xy"

#Format:  ?
#Logic:   Specifies zero or one matches; for example, \w? or (abc)?.
#         Equivalent to {0,1}.
 "abc" -match "\w?"

#Format:  {n}
#Logic:   Specifies exactly n matches; for example, (pizza){2}.
 "abc" -match "\w{2}"

#Format:  {n,}
#Logic:   Specifies at least n matches; for example, (abc){2,}.
 "abc" -match "\w{2,}"

#Format:  {n,m}
#Logidc:   Specifies at least n, but no more than m, matches.
 "abc" -match "\w{2,3}"
 
 
$list = "one","two","two","three","four","five"
$list
$list | sort | get-unique
set-content c:\knowledge\github\powershell\test.txt "welcome secontent"
set-content c:\knowledge\github\powershell\test1.txt " secontent"
# get-content c:\knowledge\github\powershell\test.txt | measure-object -character -line -word
Compare-Object -ReferenceObject $(Get-Content c:\knowledge\github\powershell\test.txt) -DifferenceObject $(Get-Content c:\knowledge\github\powershell\test1.txt)
$A = Get-ChildItem c:\knowledge\github\powershell\*.txt
Format-List -InputObject $A
Format-Wide -InputObject $A
# get stopped services
Get-Service | Where-Object {$_.Status -eq "Stopped"}
Get-Process | Where-Object {$_.ProcessName -Match "^powershell_ise.*"}
Get-ChildItem c:\knowledge\github\powershell -Name
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | ForEach-Object {$_.Split(".")}
Start-Sleep -s 1
# $choice = Read-Host "Please put your choice"
# $choice
Get-Process | Sort-Object -Property WS | Select-Object -Last 5
Get-Process | Select-Object -Property ProcessName, Id, WS -Last 5
Write-Warning  "Test Warning"
Write-Host (2,4,6,8,10,12) -Separator ", -> " -ForegroundColor DarkGreen -BackgroundColor White
# Invoke-Item "C:\knowledge\github\powershell\powershell_DateTime_Operations.ps1"
Measure-Command { Get-EventLog "Windows PowerShell" }
Invoke-History
Measure-Command { Get-EventLog "Windows PowerShell" }
Get-History
Get-Alias
get-culture
$list | Get-Member
$array = @("item1", "item2", "item3")
for($i = 0; $i -lt $array.length; $i++){ $array[$i] }
$list.getType()
