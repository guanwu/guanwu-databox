# guanwu-databox

## Databox Worker
### How to build
```
dotnet publish .\src\Databox.Applications\Databox.WorkerConsole -o .\publish\Databox.WorkerConsole -c Release -r win10-x64 --sc -p:PublishSingleFile=true -p:PublishReadyToRun=true
```
### How to deploy
```
@echo off
cd %~dp0
Databox.WorkerConsole.exe "backplane open"
pause
```
## Databox Master
### How to build
```
dotnet publish .\src\Databox.Applications\Databox.MasterConsole -o .\publish\Databox.MasterConsole -c Release -r win10-x64 --sc -p:PublishSingleFile=true -p:PublishReadyToRun=true
```
### How to deploy
```
@echo off
cd %~dp0
Databox.MasterConsole.exe "backplane open --audiences [WORKER_ACCESS_KEY]"
pause
```
## Guanwu Backplane Server

## Quick start
You need to create your own [OpenID connect discovery endpoint](https://openid.net/specs/openid-connect-discovery-1_0.html) first. 
It's ok to replace Authing.cn OpenID with any third-party authentication service compatible with Bear authentication.

For testing, just connect the following push server endpoint and two test client credentials.
```
url: https://backplane.guanwu.com/hub
app-id: 6173998e7e9e139b6824a97e
```
For Worker Console
```
access-key: 6173c355b543fee2121c0c05
secret-key: 6a62cd5015976060b5975ac91c7be0eb
```
For Master Console
```
access-key: 6174043f2aee5f89831968b7
secret-key: a632b25598c7b606fa1a36d8cb2ef119
```
