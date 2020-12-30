# Ambiente desarrollo
## Dependencias en Choco
1. Descargar Chocolatey
```powershell
Set-ExecutionPolicy AllSigned
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```

2. Validar que se instalo Choco
```powershell
choco
```

3. Instalar dependencias
```powershell
choco install nodejs-lts
choco install git
choco install vscode
choco install javaruntime
choco install jdk8
choco install sql-server-management-studio
choco install androidstudio

npm install -g cordova
npm install -g typescript
npm install -g ionic
```
4. Entrar a Android Studio -> Configure -> SDK Manager. Y descargar Android API 27, API 28 y Android SDK Tools

5. Agregar las variables de ambiente
Seguir estas instrucciones con atención: [https://cordova.apache.org/docs/en/latest/guide/platforms/android/index.html#setting-environment-variables](https://cordova.apache.org/docs/en/latest/guide/platforms/android/index.html#setting-environment-variables)

## Software por separado
### Visual Studio
1. Descargar e instalar Visual Studio Community Editio
https://visualstudio.microsoft.com/vs/community/
2. En el menu de modulos a instalar hay que elegir los siguientes:
- .NET desktop enviroment
- ASP.NET and web development
![modules](https://visualstudio.microsoft.com/wp-content/uploads/2017/02/Community-page-installer-1.png)
3. Para utilizar DevExpress es necesario hablar con algún otro miembro del equipo

### Nuget
1. Descargar la última versión de Nuget en el directorio `C:/bin`
https://www.nuget.org/downloads
2. ¡OJO! No correr el ejecutable de descarga
3. Navegar a las variables de ambiente y en la variable `Path` agregar `C:/bin`
![enviroment](https://trevorsullivan.net/wp-content/uploads/2016/07/Environment-Variables.png)
4. Crear un PAT (Personal Access Token)  
[Aquí como generar uno](https://help.github.com/en/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line), el token tiene que todos los accesos a `repo` y `write:packages`, `read:packages`, y `delete:packages`.  
*Este token es único y no vuele a salir, guardenlo bien*
5. Correr el siguiente comando:
```bash
nuget sources add -name "Github Packages" -Source https://nuget.pkg.github.com/procesoseficientes/ind
ex.json -Username <usuario de github> -Password <PAT>
```