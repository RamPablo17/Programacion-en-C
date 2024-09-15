<h1> Tema 5 - Sentencias de control y bucles.</h1>
<h2>5.1 - Sentencia de control if.</h2>

<p>Antes de empezar a explicar las sentencias de control del lenguaje C, conviene explicar los conceptos de verdadero/falso y de sentencia que posee el lenguaje C.<br><br>
El lenguaje C posee un concepto muy amplio de lo que es verdadero. Para C,cualquier valor que sea distinto de cero es verdadero, siendo por tanto falso solo si el
valor cero. Es por ello que una expresión del tipo if(x) será verdad siempre que el valor de la variable x sea distinto de cero, sea cual sea el tipo de la variable x.<br><br>
El concepto de sentencia en C es igual que el de otros muchos lenguajes. Por sentencia se entiende en C cualquier instrucción simple o bien, cualquier conjunto de
instrucciones simples que se encuentren encerradas entre los caracteres { y }, que marcan respectivamente el comienzo y el final de una sentencia.<br><br>
La forma general de la sentencia if es:<br>
if (condición<br>
&nbsp sentencia;<br>
else<br>
&nbsp sentencia;<br><br>
Siendo el else opcional. Si la condición es verdadera se ejecuta la sentencia asociada al if, en caso de que sea falsa la condición se ejecuta la sentencia asociada al else (si existe el else). Veamos algunos ejemplos de sentencias if:
</p>
