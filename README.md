# Examen_Sistema-Bauhaus-Reactivo
Nombre del Proyecto:
**Sistema Bauhaus Reactivo**

Autor: [Benjamín Rocco]

**Link p5js**

[*https://editor.p5js.org/benjamin.rocco/sketches/jDdAW2eUa*]

## 1. Descripción

Este proyecto es un sketch interactivo desarrollado en p5.js. En pantalla se genera una composición visual formada por módulos geométricos organizados en grillas.
Cada módulo está compuesto por tres formas concéntricas que cambian de color, tamaño y forma durante la ejecución del programa.

El sistema tiene tres estados visuales, activados con las teclas 1, 2 y 3. Cada estado modifica la densidad de la grilla y la cantidad de módulos visibles en pantalla.
La interacción ocurre a través del mouse, el teclado y el sonido. La posición horizontal del mouse controla el tamaño base de los módulos; al presionar el mouse, las formas cambian de círculos a cuadrados; y la amplitud del sonido modifica el tamaño de los elementos visuales.

El resultado es una composición generativa y reactiva, donde la imagen cambia constantemente a partir de reglas programadas, valores aleatorios e inputs del usuario

## 2. Inputs y outputs

*Inputs*

- Inputs interactivos

*1. Movimiento horizontal del mouse (mouseX)*

Controla el tamaño base de los módulos mediante la función map().

*2. Mouse presionado (mouseIsPressed)* cambia la forma de los módulos.

Si el mouse **está presionado**, los módulos se dibujan como **cuadrados**.

Si el mouse no **está presionado**, los módulos se dibujan como **círculos**.

*3. Teclado (keyPressed)* permite cambiar entre los tres estados del sistema:

*Tecla 1:* Estado 1, grilla ordenada.
 
*Tecla 2:* Estado 2, grilla más densa.

*Tecla 3:* Estado 3, grilla saturada.

- Multimedia
  
 *Imagen de fondo (fondo.jpg)*

Funciona como una textura visual secundaria que acompaña la composición modular.

 *Sonido (glitch.mp3)*

El sonido se activa al presionar una tecla. Luego, el programa mide su amplitud mediante p5.Amplitude() y usa ese valor para modificar el tamaño de los módulos. 
De esta manera, el audio no funciona solo como acompañamiento, sino como un elemento que influye en el comportamiento visual del sistema.


*Outputs*

El sistema genera un output visual dinámico compuesto por:

- Módulos geométricos circulares o cuadrados.

- Cambios de tamaño controlados por el mouse y por la amplitud del sonido.
  
- Variaciones aleatorias de color mediante random().

- Tres estados visuales con distinta densidad.

- Una textura de fondo que refuerza la atmósfera visual.

- Una composición reactiva que cambia constantemente durante la ejecución del programa.

## 3. Sistema

El funcionamiento del sistema se organiza en una estructura de entrada, procesamiento y salida.

Primero, en **preload()**, se cargan los archivos multimedia del proyecto, una imagen de fondo y un sonido. Luego, en **setup()**, se crea el canvas, se define el modo de dibujo de los rectángulos y se configura el medidor de amplitud del sonido.

En **draw()**, el programa se actualiza constantemente. La posición horizontal del mouse se transforma en un valor de tamaño mediante *map(mouseX, 0, width, 60, 100)*. Ese valor se limita para que no sea menor a 60 ni mayor a 100. Después, el sistema mide el volumen del audio con *amplitud.getLevel()* y transforma ese valor en una variable llamada *reaccionSonido*, que se suma al tamaño de cada módulo.

Cada estado utiliza bucles *for()* para recorrer posiciones dentro de una grilla. En cada posición se generan colores aleatorios con *random(3)* y se calcula el tamaño final del módulo. Luego se llama a la *función dibujarModulo()*, que decide si dibujar círculos o cuadrados según el estado del mouse.

**Estados** del sistema

*Estado 1* Orden

El primer estado presenta una grilla más espaciada, con módulos ubicados entre las coordenadas principales del canvas. Este estado funciona como una composición más estable y ordenada.

*Estado 2* Densidad

El segundo estado aumenta la cantidad de módulos, reduciendo la distancia entre filas y columnas. Esto genera una sensación de mayor acumulación visual y transición hacia la saturación.

*Estado 3* Saturación

El tercer estado ocupa casi toda la pantalla con una grilla más cerrada. La composición se vuelve más intensa, densa e inestable. Este estado representa el punto de mayor saturación del sistema.

## 5. Elementos técnicos utilizados

El proyecto incorpora los siguientes recursos técnicos:

 - Variables propias: tamano, estado, fondo, sonido, amplitud, reaccionSonido.

 - Condicionales: control de tamaño, selección de estado, selección de color, cambio entre círculo y cuadrado.

 - Funciones propias: elegirColor() y dibujarModulo().

 - Bucles: bucles for anidados para recorrer filas y columnas.

 - map(): mapea el tamaño de los modulos entre rangos con el input mouseX

 - random(): genera variación de color y tamaño.

 - Input interactivo: mouse, teclado y sonido.

 - Output visual dinámico: grilla modular reactiva.

 - Tres estados visuales.

 - Multimedia: imagen de fondo y sonido.

## 6. Marco conceptual

El proyecto toma como punto de partida la **Bauhaus**, principalmente por su uso de formas geométricas simples, grilla, color y composición modular. Esta referencia ya estaba presente en mi Solemne II, donde trabajé con una composición basada en círculos, repetición y variaciones cromáticas.

Para el examen, retomé esa base visual con el objetivo de transformarla en un sistema más interactivo. La composición deja de funcionar como una imagen fija y pasa a responder al usuario mediante el mouse, el teclado y el sonido. De esta manera, la lógica modular inspirada en la Bauhaus se adapta al lenguaje de la programación creativa.

El sistema trabaja entre el orden y la interferencia. La grilla organiza la composición, mientras que *random()*, la amplitud del sonido y los cambios de estado introducen variaciones que modifican el resultado visual en tiempo real. Así, las formas geométricas dejan de ser elementos estáticos y se convierten en módulos reactivos.



## 7. Referente principal

*Bauhaus [Poster de la Bauhaus Ausstellung 1923] / Solemne II [*https://editor.p5js.org/benjamin.rocco/sketches/U-lbY0VQc*]*

El referente principal del proyecto es la **Bauhaus**, entendida desde su relación con la geometría, la síntesis formal y la organización visual mediante estructuras modulares. Me interesó tomar esta referencia porque permite construir una composición clara a partir de elementos básicos como círculos, cuadrados, color y repetición.

También tomo como referencia directa mi proyecto de **Solemne II**, ya que este examen funciona como una evolución de esa primera exploración. En la versión anterior, el sistema tenía una interacción más limitada; en esta nueva versión busqué mejorar su comportamiento, incorporando tres estados, reacción al sonido, cambios de forma y mayor variación visual.

La propuesta no busca copiar literalmente la Bauhaus, sino reinterpretarla desde un contexto digital. Por eso, el proyecto mantiene una base geométrica y modular, pero la vuelve dinámica, reactiva y audiovisual.


## 8. Decisiones visuales y sonoras

La paleta de color utiliza tonos azules, celestes y azul profundo. Estos colores buscan dar una sensación de modernidad, actualidad y lenguaje digital. Aunque el proyecto parte desde una referencia histórica como la Bauhaus, la paleta permite actualizar esa influencia hacia una estética más contemporánea.

Los módulos están construidos con tres capas concéntricas, lo que permite mantener una identidad visual clara en los distintos estados. A medida que el sistema cambia, varían la densidad, el tamaño, el color y la forma, pero se conserva una estructura reconocible.

El fondo funciona como una textura secundaria que introduce interferencia visual. Esta capa tensiona la limpieza geométrica de la grilla y refuerza la idea de un sistema que no permanece completamente estable.

El sonido también participa en el comportamiento visual. Su amplitud modifica el tamaño de los módulos, generando una relación directa entre audio e imagen. Esto permite que el proyecto no dependa solo de la interacción manual, sino también de una respuesta audiovisual.

## 9. Reflexión final

El desarrollo de este proyecto me permitió transformar una exploración visual que ya había iniciado en mi Solemne II en un sistema interactivo más completo. Al comienzo, la composición funcionaba principalmente desde la repetición de módulos geométricos, pero durante el proceso fui incorporando nuevas capas de interacción que modifican su comportamiento en tiempo real.

Una de las decisiones más importantes fue no abandonar la lógica visual inicial, sino adaptarla mejor al lenguaje de la programación. La grilla, los círculos y los cuadrados se mantuvieron como base del proyecto, pero dejaron de operar como elementos estáticos. A través del uso de *map(), random(), condicionales, bucles y funciones propias*, la composición comenzó a responder al mouse, al teclado y al sonido.

También fue importante ajustar el equilibrio entre control y variación. En varias etapas, el sistema podía volverse demasiado caótico o perder legibilidad, especialmente por el uso de *random()* y por la reacción del sonido. Por eso fui modificando los rangos de tamaño y la intensidad de la amplitud sonora hasta encontrar un punto medio donde la composición se sintiera dinámica, pero todavía clara y coherente.

El sonido fue una incorporación clave, porque permitió que el proyecto no dependiera solo de la interacción manual. Al medir la amplitud del audio y usarla para modificar el tamaño de los módulos, el sistema adquirió una dimensión audiovisual más evidente. Esto reforzó la idea de una Bauhaus reinterpretada desde un contexto digital y actual, donde la geometría ordenada convive con la interferencia, el movimiento y la reacción computacional.

Durante el proceso también comprendí mejor la estructura interna de un programa interactivo, la diferencia entre inputs, procesos y outputs; la función de los estados; el uso de condicionales booleanos; y la importancia de ordenar el código para poder explicarlo. Más que sumar elementos visuales sin control, el desafío fue tomar decisiones que tuvieran sentido dentro del sistema.

El resultado final busca mostrar una evolución entre orden, densidad y saturación. A partir de una base geométrica inspirada en la Bauhaus, el proyecto propone una composición reactiva que cambia según la acción del usuario, el azar y el sonido. Esta experiencia me ayudó a entender que programar no es solo escribir código, sino construir reglas visuales capaces de producir comportamiento, variación y sentido.
