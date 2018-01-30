# Arquitecturas software para la nube

## Ejercicio 1

Buscar una aplicación de ejemplo, preferiblemente propia, y deducir qué patrón es el que usa. ¿Qué habría que hacer para evolucionar a un patrón tipo microservicios?


La aplicación a desarrollar para esta asignatura, consta de una API REST para servir datos de jugadores, asi como su correspondiente base de datos por lo que utilizaría una arquitectura basada en microservicios. Para poder escalar este tipo de patrón se pueden separar servicios en distintas unidades o replicar aquellos que tengan más carga y supongan un cuello de botella.

## Ejercicio 2

En la aplicación que se ha usado como ejemplo en el ejercicio anterior, ¿podría usar diferentes lenguajes? ¿Qué almacenes de datos serían los más convenientes?

En la aplicación anterior, al ser básicamente una API REST, podría usar cualquier lenguaje que permita su desarrollo. En cuanto a que tipo de almacén de datos he optado por una base de datos no relacional o no SQL, dada que la estructura y cantidad de los datos puede variar según el juego que lo requiera y de esta forma no es necesaria crear una nueva tabla para cada juego añadido. 
