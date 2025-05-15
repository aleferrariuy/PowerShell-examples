## Desinstalar software desde PowerShell

### Abrir como Administrador la consola de PowerShell

#### Ejecutar
~~~
PS C:\Windows\system32> Get-AppXPackage | select name | sort name
~~~

#### Salida (ejemplo)
~~~
Name
----
1527c705-839a-4832-9118-54d4Bd6a0c89
5319275A.WhatsAppDesktop
c5e2524a-ea46-4f67-841f-6a9465d9d515
CanonicalGroupLimited.Ubuntu24.04LTS
E2A4F912-2574-4A75-9BB0-0D023378592B
F46D4000-FD22-4DB4-AC8E-4E1DDDE828FE
Microsoft.549981C3F5F10
Microsoft.AAD.BrokerPlugin
Microsoft.AccountsControl
Microsoft.AsyncTextService
Microsoft.AV1VideoExtension
Microsoft.BingSearch
Microsoft.BioEnrollment
Microsoft.CredDialogHost
Microsoft.DesktopAppInstaller
Microsoft.ECApp
Microsoft.GetHelp
Microsoft.HEIFImageExtension
Microsoft.LanguageExperiencePackes-ES
Microsoft.LockApp
Microsoft.MicrosoftEdge.Stable
Microsoft.MicrosoftEdgeDe
~~~

#### Seleccionar y copiar nombre de la aplicación a remover (en este ejemplo, WhatsApp)
Confirmar si es la correcta
~~~
PS C:\Windows\system32> Get-AppXPackage -Name '5319275A.WhatsAppDesktop'


Name              : 5319275A.WhatsAppDesktop
Publisher         : CN=24803D75-212C-471A-BC57-9EF86AB91435
Architecture      : X64
ResourceId        :
Version           : 2.2518.3.0
PackageFullName   : 5319275A.WhatsAppDesktop_2.2518.3.0_x64__cv1g1gvanyjgm
InstallLocation   : C:\Program Files\WindowsApps\5319275A.WhatsAppDesktop_2.2518.3.0_x64__cv1g1gvanyjgm
IsFramework       : False
PackageFamilyName : 5319275A.WhatsAppDesktop_cv1g1gvanyjgm
PublisherId       : cv1g1gvanyjgm
IsResourcePackage : False
IsBundle          : False
IsDevelopmentMode : False
NonRemovable      : False
Dependencies      : {Microsoft.UI.Xaml.2.8_8.2501.31001.0_x64__8wekyb3d8bbwe,
                    Microsoft.NET.Native.Framework.2.2_2.2.29512.0_x64__8wekyb3d8bbwe,
                    Microsoft.NET.Native.Runtime.2.2_2.2.28604.0_x64__8wekyb3d8bbwe,
                    Microsoft.VCLibs.140.00_14.0.33519.0_x64__8wekyb3d8bbwe...}
IsPartiallyStaged : False
SignatureKind     : Store
Status            : Ok
~~~

#### Remover ejecutando
~~~
PS C:\Windows\system32> Get-AppXPackage -Name '5319275A.WhatsAppDesktop' | Remove-AppxPackage
~~~

✔ Una correcta ejecución, no debe devolver ninguna salida al shell

❌ Si surge un error, se detallará en un mensaje con letras rojas

⚜ Es muy importante el tener en cuenta que, es válido el utilizar carácteres _comodín_ como "\*" ( todo lo que comienza con Microsoft = Microsoft\* )
