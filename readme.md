# Filtros en CSS #

## Introducción a Filtros ##
La propiedad filter nos va a permitir aplicar efectos gráficos a nuestras imágenes. Se suele utilizar para galería de imágenes y ese tipo de diseños.

Hay que tener en cuenta que filter es una propiedad que crea un nuevo contexto de apilamiento, eso puede generar problemas con el z-index causando ocultamientos de elementos.

Su sintaxis es:

`` filter: funcion(valor); ``


## blur(px) ##
Aplica un desenfoque Gaussiano a la imagen. El valor de 'radio' (valor que le damos) define el número de pixeles que se mezclan entre sí, por lo que un valor mayor, logrará un desenfoque mayor.

Cabe destacar, que el valor siempre tiene que estar dado en pixeles.

Se suele utilizar en el pseudoelemento :hover

Ejemplo:
`` filter: blur(5px); ``


## brightness(number || %) ##
Aplica una multiplicación lineal a la imagen, haciendo que parezca más o menos **brillante**. Admite valores numéricos y en porcentajes.

Si utilizamos valores numéricos, 1 es el valor por defecto y 0 será sin brillo.

Si utilizamos valores de porcentaje, 100% será el valor por defecto y 0% será sin brillo.

Cabe destacar, que es mucho más común utilizar valores numéricos

Ejemplo:
`` filter: brightness(.5) ``


## contrast(number || %) ##
Ajusta el contraste de la imagen de entrada. Es decir, un valor por debajo de 100% disminuye el contraste y un valor por encima de 100% aumenta el contraste.

Por defecto, el valor es 100%.

Ejemplo:
`` filter: contrast(50%); ``
Mientras menor sea el porcentaje, más grís se volverá la imagen.


## grayscale(number || %) ##
Un valor de 100% es completamente en escala de grises, mientras que un valor de 0% deja la entrada sin cambios.

Ejemplo:
`` filter: grayscale(100%); ``

Si el valor está en 100%, la imagen será blanco y negro.

Si el valor está en 0, la imagen estará como por defecto.


## hue-rotate(angle) ##
El cambio relativo en el tono de la muestra de entrada (la imagen por defecto). 

Un valor de 0deg deja la entrada sin cambios. Una rotación de tono positiva aumenta el valor de tono. 

Mientras que una rotación de valor negativa, reduce el valor del tono.

Ejemplo:
`` filter(hue-rotate(50deg)); ``

- El angle 0 (color rojo)
- El angle 30 (color naranja)
- El angle 60 (color amarillo)
- El angle 90 (color verde claro)
- El angle 120 (color verde)
- El angle 150 (color verde-cian)
- El angle 180 (color cian)
- El angle 210 (color azul claro)
- El angle 240 (color azul)
- El angle 270 (color violeta claro)
- El angle 300 (color rosa)
- El angle 330 (color rosa-rojo)


## invert(number || %) ##
Este filtro, invierte el color a su contrario en el círculo cromático. Un valor de 100% o de 1 hace que el color esté completamente invertido, mientras que un valor de 0, deja la entrada sin cambios.

Ejemplo:

`` filter:invert(100%); ``


## opacity(number || %) ##
Este valor funciona igual que la propiedad opacity de CSS.

Un valor de 0 es completamente transparente, mientra que un valor de 100% deja la entrada sin cambios.

Ejemplo:
`` filter:opacity(50%); ``


## saturate(number || %) ## 
Este valor nos permite cambiar la saturación de la imagen.

Un valor por debajo de 100% desatura la imagen, mientras que un valor por encima de 100% la sobresatura.

Es decir, permite hacer los colores más vivos o apagados.

Ejemplo:

`` filter:saturate(50%); ``


## sepia(number || %) ##
Convierte la imagen de entrada a sepia, dándole una aparencia más calida, tirando a colores amarillos/marrones.

Un valor de 100% es completamente sepia, mientras que un valor de 0% deja la entrada sin cambios.

Ejemplo:
`` filter:sepia(100%); ``


## drop-shadow(offset-x offset-y blur color) ##
Aplica un efecto de sombra a la imagen de entrada, muy similar a drop-shadow.

Los valores son los mismos. 

* offset-x offset-y (requerido): Estos valores determinan el desplazamiento de la sombra. offset-x especifica la distancia horizontal, donde los valores negativos colocan la sombra a la izquierda del elemento. offset-y especifica la distancia vertical, donde los valores negativos colocan la sombra sobre el elemento.

* blur (opcional): El radio de desenfoque de la sombra, cuanto mayor es el valor, más desenfoque habrá. Si no se especifica, el valor por defecto es 0.

* color (opcional): El color de la sombra, si no se especifica, se utiliza el valor de la propiedad.

Ejemplo:
`` filter:drop-shadow(10px 10px 20px red); ``

Sirve para las imágenes que tengan un fondo transparente y le queramos dar sombra.


## ¿Cómo aplicar distintos filtros a una imagen? ##
``filter: invert(1) sepia(1) saturate(300);``
Simplemente es ir poniendo las funciones en la posición correcta.


## Problemas con el stacking context ##
Al usar la propiedad filter, creamos un contexto de apilamiento nuevo, por ende si teniamos un título, texto, etc, estos se verán afectados y quedarán por debajo de la imagen.

Para corregir ese problema, basta con poner un ``z-index:1;`` al texto que se nos por debajo de la imagen. Ya que estamos forzando a que suba con el z-index.
