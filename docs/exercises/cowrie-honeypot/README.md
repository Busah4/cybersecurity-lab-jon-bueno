# Ejercicio sobre la creación, configuración, y testeo de una HoneyPot desde cero.

En este ejercicio vamos a instalar y configurar una HoneyPot cowrie con el objetivo de poder retrasar 
a diferentes atacantes que quieran acceder a nuestras máquinas principales.

## Objetivo

Obtener la información de los posibles atacantes a la hora de intentar acceder a la HoneyPot.

## Metodología

He creado la estructura, posteriormente he descargado los repositorios, y los he instalado
en un entorno virtual con el objetivo de que la instalación se produzca dentro de dicho entorno
virtual. Tras esto, he configurado la HoneyPot con el objetivo de que escuche conexiones
que se realicen en el puerto 22, reportando cualquier tipo de flujo de información que reciba.
Una vez realizado lo previo, he realizado una conexión a dicho puerto (e IP de la máquina) con una máquina Kali.

## Resultado de conexión con máquina Kali Linux

La conexión con la máquina Kali ha sido registrada de manera existosa, y se ha podido ver en acción
el HoneyPot, en este caso solicitando la contraseña a la máquina que se intentaba conectar, teniendo
ningún tipo de exito ya que la HoneyPot le solicitaba una contraseña que no existia. Registrando
cada intento de conexión.

## Hallazgos de Seguridad

Gracias a la HoneyPot creada, se puede ver los intentos de login no-autorizados pudiendo realizar
un informe con la información de los diferentes atacantes.

## Archivos Incluidos
cowrie.log: log con los registros de las acciones sucedidas durante tanto la creación de la HoneyPot 
como tras el intento de conexión.

## Conclusión
La HoneyPot fue efectiva a la hora de bloquear y documentar mediante los logs la información de 
los atacantes.
