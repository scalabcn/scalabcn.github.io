---
layout: post
title:  "Enunciado Args Kata"
date:   2017-02-12 16:09:04 +0100
---

La mayoría de nosotros hemos tenido que analizar los argumentos de línea de comandos alguna vez. Si no tienen una gran utilidad, entonces símplemente recorremos el array de strings que han sido pasados a la función main. Hay varias utilidades disponibles para el tratamiento de estos argumentos, pero probablemente no hacen exactamente lo que queremos. ¡Así que vamos a escribir otra! :)

Los argumentos que se pasan al programa consisten en flags y valores. Los flags son un caracter precedidos por un signo menos '-'. Cada flag tiene cero o un valor asociadao a él.

Debes escribir un analizador para este tipo de argumentos. Este analizador tiene un esquema que detalla cuáles son los argumentos que el programa espera. El esquema especifica el número, tipo de flags y valores que el programa espera.

Una vez que el esquema se ha especificado, el programa le pasará la lista de argumentos reales al analizador de argumentos. Se verificará que los argumentos coinciden con el esquema. El programa entonces, puede preguntar al analizador de argumentos por cada uno de los valores usando el nombre de los flags. Los valores son devueltos con sus tipos correctos, los cuales han sido especificados en el esquema.

Por ejemplo, si el programa se llama con los siguientes argumentos:

```
-l -p 8080 -d /usr/logs
```

esto indica un esquema con 3 flags: l, p y d. La 'l' (de logging) no tiene valor asociada a él, es un flag booleano que si está presente vale verdadero, de lo contrario vale falso. La bandera 'p' (de port) tiene un valor entero y la bandera 'd' (directory) tiene un valor de cadena de texto.

Si un flag se menciona en el esquema y no se pasa como argumento, se devolverá un valor por defecto. Por ejemplo false para un flag booleano, 0 para un flag numérico y '' (cadena vacía) para un flag de cadena de texto. Si los argumentos dados no coinciden con el esquema, es importante presentarle al usuario un buen mensaje de error, explicándole exáctamente qué es lo que está mal.

Si te sientes con ganas, extiende tu código para soportar la siguiente lista de argumentos:

```
-g this,is,a,list -d 1,2,-3,5
```

donde el flag 'g' indica una lista de cadenas ['this', 'is', 'a', 'list'] y donde el flag 'd' indica una lista de enteros [1, 2, -3, 5]

Asegúrate de que tu código es extensible.

### Pista

El formato del esquema y cómo se debe de especificar está deliveradamente poco comentado en la descripción de la kata. Una parte importante de la kata es el diseño de un formato conciso pero legible para ello.

### Caso de prueba sugerido

* Asegúrate de tener una prueba con un número entero negativo.
* El orden de los argumentos no tiene por qué coincidir con el orden indicado en el esquema.
* Escribe algunas pruebas para comprobar que los valores por defecto has sido asignados correctamente si algunos flag del esquema no se han pasado como argumentos.

------------

Fuente Original: [http://www.solveet.com/exercises/Kata-Args/19](http://www.solveet.com/exercises/Kata-Args/19)