# Crear un nuevo proyecto en Ionic 2

    ionic start nombre_app blank
    ionic start nombre_app sidemenu
    ionic start nombre_app tabs

# Ejecutar ionic en el navegador

Para ejecutar la aplicación de Ionic entras al directorio donde se encuentra tu aplicación.

    nombre_aplicacion ionic serve

# Definir las variables de entorno en Ubuntu 16.04 al archivo (.bashrc)

Se edita el archivo que se encuentra en la ruta **/home/nombre_usuario/**, para ver el archivo tienes que mostrar tus archivos ocultos, de lo contrario no lo veras.
Agregas estas lineas al final del archivo:

    export ANDROID_HOME=~/Android/Sdk
    export PATH=$ANDROID_HOME/platform-tools:$PATH
    export PATH=$ANDROID_HOME/tools:$PATH

# Verificar que las variable esten correctamente

    echo $ANDROID_HOME

# Generar una nueva clave para la aplicación

    keytool -genkey -v -keystore Ionic2Components.keystore -alias ionic2components -keyalg RSA -keysize 2048 -validity 10000

# Añadir plataforma android/iOS a tu proyecto de Ionic

Para ejecutar una aplicación de ionic en dispositivos android hay que añadir la plataforma para luego generar el APK y probar tu aplicación, en un dispositivo fisico. A continuación te dejo los comandos para agregar la plataforma dependiendo que SO estes usándo:
    
    $ ionic cordova platform 
    $ ionic cordova platform add ios
    $ ionic cordova platform add android

Para eliminar una plataforma ejecutas el siguiente comando y para añadirlo nuevamente usas el comando anterior.

    $ ionic cordova platform rm android
    $ ionic cordova platform rm ios

# Generar un archivo APK en ionic 2

Para generar un APK para android, previamente debiste haber definido la variable de entorno.

    ionic cordova build android

Si al momento de generar el archivo apk te marca error, instala gradle, después vuelves a realizar el paso anterior:

    sudo apt-get install gradle

# Ubicar el archivo APK generado de tu aplicación

    /home/nombre_usuario/Documentos/MiAplicacion/platforms/android/build/outputs/apk/android-debug.apk

# Añadir plugin whitelist de cordova

    cordova-plugin-whitelist

# Ejecutar ionic en el dispositivo

    ionic cordova run android --device

# Ejecutar este comando cuando mande error de app-script

    npm run ionic:serve

# Actualizar ionic app script más reciente
    
    npm install @ionic/app-scripts@nightly
    npm install @ionic/app-scripts@latest --save-dev

# Verificar versión de ionic

Entrar al directorio de donde se encuentra tu aplicación y desde ahi ejecutar el siguiente comando:
    
    ionic info

# No seguir el track de archivos modificados

Este comando sirve para evitar un seguimiento del o archivos modificados dentro de un directorio
    
    git update-index --no-assume-unchanged <nombre_directorio_o_archivo>

Instalar gulp
sudo npm install -g gulp

Checar version de de gulp
gulp -v

# Sitios de documentación de referencia

[Cordova](https://cordova.apache.org/docs/en/latest/guide/platforms/android/)
[Cordova plugin whitelist](https://github.com/apache/cordova-plugin-whitelist#network-request-whitelist)
***Para ejecutar en versiones anteriores de Android SO 4.0 ICS***
[Cordova plugin crosswalk-webview](https://github.com/crosswalk-project/cordova-plugin-crosswalk-webview)

# Aumentar el número de observables en Linux

Sitio de referencia [Jest](https://github.com/facebook/jest/issues/3254#issuecomment-297214395)
    echo fs.inotify.max_user_watches = 524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p
