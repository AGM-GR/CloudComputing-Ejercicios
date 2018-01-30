# Desarrollo basado en pruebas

## Ejercicio 1

Instalar alguno de los entornos virtuales de node.js (o de cualquier otro lenguaje con el que se esté familiarizado) y, con ellos, instalar la última versión existente, la versión minor más actual de la 4.x y lo mismo para la 0.11 o alguna impar (de desarrollo).


En este ejercicio vamos a crear un entorno virtual de node.js con `nave`, lo primero será instalar nave desde el gestor de paquetes para node:

`npm install -g nave`

E inicializaremos nuestro entorno virtual situándonos en la carpeta correspondiente a nuestro proyecto y ejecutando:

`nave use naveenv x.y`

Donde naveenv es el nombre de nuestro environment y x.y indica que se instale la version mayor y minor.

## Ejercicio 3

Crear una descripción del módulo usando package.json. En caso de que se trate de otro lenguaje, usar el método correspondiente.


Para inicializar el archivo package.json podemos ayudarnos del comando `npm init` el cual nos guia para hacer un archivo inicial al cual nos falta completar con las dependencias. El contenido del archivo final sería:

    {  
     "name": "cc",  
     "version": "1.0.0",  
     "description": "Servidor de datos de jugadores",  
     "main": "Jugadores.js",  
     "scripts": {  
       "test": "echo \"Error: no test specified\" && exit 1"  
     },  
     "dependencies": {"mongodb": "3.6.2"},  
     "devDependencies": {},  
     "optionalDependencies": {},  
     "engines": {  
     "node": ">=0.8"  
     }  
     "author": "Alejandro Guerrero Martínez",  
     "license": "GPL-3.0"  
    }
