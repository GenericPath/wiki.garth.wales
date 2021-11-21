---
description: Not the transparent kind
---

# Windows

{% hint style="info" %}
Windows cannot verify the servers identity popup:

* Connection properties -> Authentication -> Settings -> Uncheck Verify at the top
{% endhint %}

{% hint style="info" %}
To change modified data/time on files

* [ ] Open CMD Prompt as administrator
* [ ] DATE {enter}
* [ ] enter date
* [ ] TIME {enter}
* [ ] enter time
* [ ] COPY /B \<filename>+,,
{% endhint %}

{% hint style="info" %}
If command prompt won't open (just flashes briefly opening and closing)\
\
PowerShell

```
echo off
reg delete "HKCU\Console" /f
reg delete "HKCU\Software\Microsoft\Command Processor" /v "AutoRun" /f
reg delete "HKLM\Software\Microsoft\Command Processor" /v "AutoRun" /f
reg delete "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Options\cmd.exe" /f
echo done
```

This also solves git bash not opening, if git bash is using cmd prompt
{% endhint %}

