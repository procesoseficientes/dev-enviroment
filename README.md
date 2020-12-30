# Ambiente desarrollo
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