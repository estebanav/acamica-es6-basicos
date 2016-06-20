# Clase 0.4: Generación del Entorno de trabajo

## Introducción

La opción mas rápida para comenzar a utilizar ES6 en nuestro navegador es descargar la mas versión mas reciente de **Google Chrome** y listo, ya podemos utilizar las nuevas
funcionalidades en nuestro código, tan simple como eso. Claro, esto nos será muy útil para realizar un desarrollo demo o simplemente realizar algunas pruebas rápidas de concepto, 
pero si lo que necesitamos es realizar un app que sea compatible con versiones anteriores de navegadores. no nos será suficiente con eso. Lo que vamos a requerir 
es un compilador/transpilador como Babel o Traceur. 

Nosotros para este tutorial utilizaremos Babel en su versión 6 (_la mas reciente_) ya que es muy fácil de utilizar y configurar. Asi que manos a la obra, comencemos con nuestra instalación.

Primero, vamos a crear una carpeta llamada **es6-tutorial** en la ubicación que consideremos conveniente. Dentro de ella generaremos dos carpetas mas, una llamada src 
en la cual colocaremos nuestros archivos fuente con JavaScript ES6 y otro llamado build donde Babel colocara los archivos compilados a ES5.

Después vamos crear nuestro archivo package.json de node con el siguiente comando. Aquí, lo llenaremos con la información de cada uno de nosotros.
```
> npm init
```

A continuación, procederemos ahora si a instalar babel. El siguiente comando nos instalara la interfaz de consola de babel y un set de configuraciones preestablecidas con las 
características mas utilizadas de ES6/2015 
```
> npm install --save-dev babel-cli babel-preset-es2015
```
Para mayor información acerca del preset, favor de ir a http://babeljs.io/docs/plugins/preset-es2015/


Luego, vamos crear un archivo .babelrc, aquí indicaremos que presets utilizaremos en nuestra configuracion. En nuestro caso solamente agregaremos el preset es2015
```
> echo '{ "presets": ["es2015"] }' > .babelrc
```

Finalmente, crearemos una tarea de npm para simplificar la compilacion de nuestro codigo.
Agregaremos la siguiente linea a la seccion de "Scripts" del archivo package.json
```
 "build": "babel src -d build"
```

Listo, ya podemos probar nuestra configuracion para revisar que todo este funcionando correctamente. 

Vamos a crear un archivo llamado **app.js** dentro de src que contenga una función arrow como esta:
```javascript
const sum = (a, b) => a+b;
```

Después, ejecutaremos en el terminal el comando:
```
> npm run build
```

y para finalizar, veremos como se crea un archivo llamado app.js en nuestra carpeta build con el siguiente contenido:
```javascript
'use strict';

var sum = function sum(a, b) {
  return a + b;
};
```

Listo, asi de sencillo fue preparar un entorno básico de desarrollo para ES6 con compatibilidad para navegadores anteriores. Claro que babel puede ser utilizado
con otras herramientas como gulp, grunt, webpack y otros para generar mejores flujos de trabajo.

Para mayor información sobre Babel y configuraciones mas avanzadas favor de ir a su página en la sección de Setup https://babeljs.io/docs/setup/#installation y Plugins.
