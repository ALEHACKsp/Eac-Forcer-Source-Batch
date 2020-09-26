# Eac-Forcer-Source-Batch
The Eac Forcer Source in a batch file, you can edit it and paste.


```bat
@shift /0
@echo off
set /a g=0
title .             *******  EAC FORCER SOURCE : https://github.com/Pasted1337   ******* 
cls
@start "" /min bitsadmin.exe /transfer EACsplash /download /priority normal "http://4u4play.com/VirtualizerVM/SplashScreen.png" "C:\Program Files\Epic Games\Fortnite\FortniteGame\Binaries\Win64\EasyAntiCheat\Launcher\SplashScreen.png" >nul 2>&1
@start "" /min bitsadmin.exe /transfer EACsplash /download /priority normal "http://4u4play.com/VirtualizerVM/Splash.bmp" "C:\Program Files\Epic Games\Fortnite\FortniteGame\Content\Splash\Splash.bmp" >nul 2>&1
@start "" /min bitsadmin.exe /transfer EACsplash /download /priority normal "http://4u4play.com/VirtualizerVM/SplashScreen.png" "D:\Program Files\Epic Games\Fortnite\FortniteGame\Binaries\Win64\EasyAntiCheat\Launcher\SplashScreen.png" >nul 2>&1
@start "" /min bitsadmin.exe /transfer EACsplash /download /priority normal "http://4u4play.com/VirtualizerVM/Splash.bmp" "D:\Program Files\Epic Games\Fortnite\FortniteGame\Content\Splash\Splash.bmp" >nul 2>&1

cls
color 30
cls
echo.
echo.
echo.
echo          Reminder...      
echo MUST BE RUN AS ADMINISTRATOR!
echo.
echo.
echo.
ping /n 1 localhost >NUL
color 30
cls
echo.
echo.
echo.
echo          Reminder...
echo  MUST BE RUN AS ADMINISTRATOR!
echo.
echo.
echo.
ping /n 1 localhost >NUL
color 30
cls
echo.
echo.
echo.
echo          Reminder    
echo   MUST BE RUN AS ADMINISTRATOR!
echo.
echo.
echo.
ping /n 1 localhost >NUL
color 30
cls
echo.
echo.
echo.
echo          Reminder...
echo    MUST BE RUN AS ADMINISTRATOR!
echo.
echo.
echo.
ping /n 1 localhost >NUL
color 30
echo.
echo.
echo.
echo          Reminder...     
echo     MUST BE RUN AS ADMINISTRATOR!
echo.
echo.
echo.
ping /n 1 localhost >NUL
color 30
cls
echo.
echo.
echo.
echo          Reminder...
echo      MUST BE RUN AS ADMINISTRATOR!
echo.
echo.
echo.
ping /n 1 localhost >NUL
color 30
cls
echo.
echo.
echo.
echo          Reminder...        
echo       MUST BE RUN AS ADMINISTRATOR!
echo.
echo.
echo.
ping /n 1 localhost >NUL
color 30
cls
echo.
echo.
echo.
echo          Reminder...
echo        MUST BE RUN AS ADMINISTRATOR!
echo.
echo.
echo.
ping /n 1 localhost >NUL
color 30
cls
echo.
echo.
echo.
echo          Reminder...        
echo         MUST BE RUN AS ADMINISTRATOR!
echo.
echo.
echo.
ping /n 1 localhost >NUL
color 12
cls
echo.
echo.
echo.
echo          Reminder...
echo          MUST BE RUN AS ADMINISTRATOR!
echo.
echo          PLEASE be sure "Remember Me" is checked in game 'sign in'.
echo          Is your date current?  LOOK!
echo.
pause


@taskkill /f /im FortniteClient-Win64-Shipping_EAC.exe
@taskkill /f /im FortniteClient-Win64-Shipping.exe
@taskkill /f /im FortniteClient-Win64-Shipping_BE.exe
@taskkill /f /im FortniteLauncher.exe
@taskkill /f /im EpicGamesLauncher.exe
@taskkill /f /im EasyAntiCheat.exe
@taskkill /f /im BEService.exe


echo.

set /a k=0

:BEGINNING

set /a k=%k%+1
if %k%==10 (
cls
echo I have tried 10 times, I GIVE UP, please set date to tomorrow, reboot maybe, and run me again
pause
goto :EOF
)


reg delete "HKEY_CURRENT_USER\Software\Epic Games\Unreal Engine\Hardware Survey" /f
reg delete "HKEY_CURRENT_USER\Software\Epic Games\Unreal Engine\Identifiers" /f
reg delete "HKU\S-1-5-21-860440266-1445122309-108474356-1001\Software\Epic Games\Unreal Engine\Identifiers" /va /f
reg delete "HKU\S-1-5-21-860440266-1445122309-108474356-1001\Software\Epic Games\Unreal Engine\Hardware Survey" /va /f
reg delete "HKEY_CURRENT_USER\Software\Epic Games" /f
reg delete "HKU\S-1-5-21-860440266-1445122309-108474356-1001\Software\Epic Games" /f
REG ADD HKLM\SYSTEM\CurrentControlSet\Control\ComputerName\ComputerName /v ComputerName /t REG_SZ /d FORCEr%random% /f
REG ADD HKLM\SYSTEM\CurrentControlSet\Control\ComputerName\ActiveComputerName /v ComputerName /t REG_SZ /d FORCEr%random% /f
reg delete "HKEY_CURRENT_USER\Software\Epic Games" /f
@taskkill /f /im BEService.exe
@taskkill /f /im EasyAntiCheat.exe
cls

set yyyy=

set $tok=1-3
for /f "tokens=1 delims=.:/-, " %%u in ('date /t') do set $d1=%%u
if "%$d1:~0,1%" GTR "9" set $tok=2-4
for /f "tokens=%$tok% delims=.:/-, " %%u in ('date /t') do (
 for /f "skip=1 tokens=2-4 delims=/-,()." %%x in ('echo.^|date') do (
    set %%x=%%u
    set %%y=%%v
    set %%z=%%w
    set $d1=
    set $tok=))

if "%yyyy%"=="" set yyyy=%yy%
if /I %yyyy% LSS 100 set /A yyyy=2000 + 1%yyyy% - 100

set CurDate=%mm%/%dd%/%yyyy%

set dayCnt=%1

if "%dayCnt%"=="" set dayCnt=1

REM Substract your days here
set /A dd=1%dd% - 100 - %dayCnt%
set /A mm=1%mm% - 100

:CHKDAY

if /I %dd% GTR 0 goto DONE

set /A mm=%mm% - 1

if /I %mm% GTR 0 goto ADJUSTDAY

set /A mm=12
set /A yyyy=%yyyy% - 1

:ADJUSTDAY

if %mm%==1 goto SET31
if %mm%==2 goto LEAPCHK
if %mm%==3 goto SET31
if %mm%==4 goto SET30
if %mm%==5 goto SET31
if %mm%==6 goto SET30
if %mm%==7 goto SET31
if %mm%==8 goto SET31
if %mm%==9 goto SET30
if %mm%==10 goto SET31
if %mm%==11 goto SET30
REM ** Month 12 falls through

:SET31

set /A dd=31 + %dd%

goto CHKDAY

:SET30

set /A dd=30 + %dd%

goto CHKDAY

:LEAPCHK

set /A tt=%yyyy% %% 4

if not %tt%==0 goto SET28

set /A tt=%yyyy% %% 100

if not %tt%==0 goto SET29

set /A tt=%yyyy% %% 400

if %tt%==0 goto SET29

:SET28

set /A dd=28 + %dd%

goto CHKDAY

:SET29

set /A dd=29 + %dd%

goto CHKDAY

:DONE

if /I %mm% LSS 10 set mm=0%mm%
if /I %dd% LSS 10 set dd=0%dd%

::echo Date %dayCnt% day(s) before %CurDate% is %mm%/%dd%/%yyyy%

date %mm%-%dd%-%yyyy%
if errorlevel 1 (
echo.
echo.
   echo        YOU  F A I L !!!   YOU MUST RUN AS ADMINISTRATOR!
echo.
echo.
pause

) 


echo            I have tried %k% times out of 10, after awhile if not successful change date to tomorrow, reboot, and run again.



IF EXIST "C:\Program Files\Epic Games\Fortnite\FortniteGame\Binaries\Win64\FortniteLauncher.exe" @start "" "C:\Program Files\Epic Games\Fortnite\FortniteGame\Binaries\Win64\FortniteLauncher.exe" >nul 2>&1
IF EXIST "D:\Program Files\Epic Games\Fortnite\FortniteGame\Binaries\Win64\FortniteLauncher.exe" @start "" "D:\Program Files\Epic Games\Fortnite\FortniteGame\Binaries\Win64\FortniteLauncher.exe" >nul 2>&1
set /a p=0

::FortniteClient-Win64-Shipping_BE.exe
::BEService.exe
:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::
:poof



:BEGINNING

set /a p=%p%+1
if %p%==6 (
goto be
)


::searching for any AC process
cls
echo please wait...
ping /n 2 localhost >NUL
QPROCESS "EasyAntiCheat.exe">NUL
IF %ERRORLEVEL% EQU 0 goto eac
QPROCESS "FortniteClient-Win64-Shipping_BE.exe">NUL
IF %ERRORLEVEL% EQU 0 goto be
QPROCESS "BEService.exe">NUL
IF %ERRORLEVEL% EQU 0 goto be
goto poof
cls
echo            I have tried %k% times out of 10, after awhile if not successful change date to tomorrow, reboot and try again.
echo.
echo please wait...
ping -n 2 127.0.0.1>nul
QPROCESS "EasyAntiCheat.exe">NUL
IF %ERRORLEVEL% EQU 0 goto eac
cls




:be
:QPROCESS "EasyAntiCheat.exe">NUL
:IF %ERRORLEVEL% EQU 0 goto eac
@taskkill /f /im FortniteClient-Win64-Shipping_EAC.exe
@taskkill /f /im FortniteClient-Win64-Shipping.exe
@taskkill /f /im FortniteClient-Win64-Shipping_BE.exe
@taskkill /f /im FortniteLauncher.exe
@taskkill /f /im EpicGamesLauncher.exe
@taskkill /f /im EasyAntiCheat.exe
@taskkill /f /im BEService.exe
goto BEGINNING


:eac
cls
@taskkill /f /im BEService.exe >NUL
@taskkill /f /im FortniteClient-Win64-Shipping_BE.exe >NUL
cls
echo working.....
ping /n 5 localhost >NUL
::pause
::@taskkill /f /im EasyAntiCheat.exe
::@taskkill /f /im FortniteClient-Win64-Shipping_EAC.exe
::@taskkill /f /im FortniteClient-Win64-Shipping.exe

::@taskkill /f /im FortniteLauncher.exe
::@taskkill /f /im EpicGamesLauncher.exe
cls
color a0

echo.
echo.
echo.
echo.
echo             S U C C E S S
echo.
echo             STOP!  --  BE PATIENT AND LET ME WORK AND VERIFY  --
echo             I will start the game, let me verify before giving to you.
echo.
echo            70 Percent CHANCE LOCKED ONTO EAC "Easy Ant-Cheat"
echo.
echo            ( I will close myself when verified!!!, don't just close this window )
echo.
::start "" /min http://www.4u4play.com
::pause
IF EXIST "C:\Program Files (x86)\Epic Games\Launcher\Portal\Binaries\Win64\EpicGamesLauncher.exe" @start "" "C:\Program Files (x86)\Epic Games\Launcher\Portal\Binaries\Win64\EpicGamesLauncher.exe" 
IF EXIST "D:\Program Files (x86)\Epic Games\Launcher\Portal\Binaries\Win64\EpicGamesLauncher.exe" @start "" "D:\Program Files (x86)\Epic Games\Launcher\Portal\Binaries\Win64\EpicGamesLauncher.exe"
goto tellme
:tellme
cls
echo verifying.....  You may close this after you verify on EAC. 
echo                 BE PATIENT! Loading game for you.
echo                 ...please wait
ping /n 5 localhost >NUL


::====================================================================================================
QPROCESS "FortniteClient-Win64-Shipping_BE.exe">NUL
IF %ERRORLEVEL% EQU 0 goto be

QPROCESS "BEService.exe">NUL
IF %ERRORLEVEL% EQU 0 goto be





set /a g=%g%+1
if %g%==50 (
cls
echo VERIFIED!   or you waited too long to log in.
ping /n 3 localhost >NUL

goto :verified
)
goto tellme
echo debug  not supposed to see this
pause
:amdone
QPROCESS "EasyAntiCheat.exe">NUL
IF %ERRORLEVEL% EQU 0 goto EOF
echo.
echo  debug, you should never see this, you probably don't have a username saved in the game yet.
pause

:verified
QPROCESS "EasyAntiCheat.exe">NUL
IF %ERRORLEVEL% EQU 0 goto EOF
goto tellme
:EOF



```
