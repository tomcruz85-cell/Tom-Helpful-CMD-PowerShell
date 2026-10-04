# Tom-Helpful-CMD-PowerShell
Has all the helpful items I use for my job here for use in cmd and powershell

PowerShell
Restart Windows Explorer:

Stop-Process -Name explorer -Force; Start-Process explorer

CMD (Run as administrator)
Clear Windows temporary files and restart the update services:

@echo off
del /s /q "C:\Windows\Temp\*.*"
del /s /q "C:\Windows\Prefetch\*.*"
net stop bits
net stop wuauserv
del /s /q "C:\Windows\SoftwareDistribution\*.*"
net start bits
net start wuauserv

Run only when Windows Update is not in progress. Windows rebuilds these caches as needed; clearing Prefetch can temporarily slow app launches, and clearing the update cache may require files to be downloaded again..
