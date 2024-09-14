<h1> Tema 2 - Identificadores, tipos de datos, variables
y constantes. </h1>

<h1> 2.1 - Identificadores.</h1>

<p>Antes de proceder a explicar los identificadores en C, es necesario resaltar que C es un lenguaje sensible al contexto, a diferencia por ejemplo de Pascal, por lo cual, C diferencia entre mayúsculas y minúsculas, y por tanto, diferencia entre una palabra escrita total o parcialmente en mayúsculas y otra escrita completamente en minúsculas.</p>

<p>En el lenguaje C, un identificador es cualquier palabra no reservada que comience por una letra o por un subrayado, pudiendo contener en su interior letras,números y subrayados. La longitud máxima de un identificador depende del compilador que se este usando, pero, generalmente, suelen ser de 32 caracteres, ignorándose todos aquellos caracteres que compongan el identificador y sobrepasen la longitud máxima. Recuérdese, además, que al ser C sensible al contexto, un identificador escrito como esto_es_un_ident y otra vez como Esto_Es_Un_Ident será interpretado como dos identificadores completamente distintos.</p>

<h1> 2.2 - Tipos de datos, modificadores de tipo y modificadores
de acceso. </h1>

<P>En C, toda variable, antes de poder ser usada, debe ser declarada, especificando con ello el tipo de dato que almacenara. Toda variable en C se declara de la forma: <tipo de dato> <nombre de variable> [, nombre de variable]; En C existen cinco tipos de datos según puede verse en la tabla siguiente: </P>

![image](https://github.com/user-attachments/assets/74759276-8285-41d7-b76d-ba236b4660cf)

<P>Algunos ejemplos de variables de C serían:<br>
float a;<br>
int b,c;<br>
char caracter,otro_caracter;</P>

<p>Existen, además, cuatro modificadores de tipo, los cuales se aplican sobre los tipos de datos anteriormente citados. Los modificadores de tipo permiten cambiar el tamaño, etc., de los tipos de datos anteriormente especificados. Estos modificadores, que sintácticamente anteceden a la declaración del tipo de dato, son:
</p>

![image](https://github.com/user-attachments/assets/c935b487-9261-4b3b-9678-dd417d3d7804)

<p>Es por ello, que podemos declarar variables como:<br>
<pre>unsigned char a;<br>
long double b;<br>
short int i;<br></pre>
Es posible, además, aplicar dos modificadores seguidos a un mismo tipo de datos, así, es posible definir una variable de tipo unsigned long int (entero largo sin
signo). El rango de valores de que permite cada variable depende del sistema operativosobre el cual se trabaje (MS-DOS, Windows95/98/NT/2000, UNIX/Linux), por lo cualconviene referirse al manual del compilador para conocerlo. De forma general, lossistemas operativos de 16 bits (MS-DOS, Windows 16 bits) poseen un rango y los de 32 bits (Windows 32 bits, UNIX/Linux) otro </p>

![image](https://github.com/user-attachments/assets/732f8c53-464e-428d-be41-d077a00c426b)

<p>Además de los modificadores de tipo existen modificadores de acceso. Los modificadores de acceso limitan el uso que puede realizarse de las variables declaradas. Los modificadores de acceso anteceden a la declaración del tipo de dato de la variable y son los siguientes:</p>

![image](https://github.com/user-attachments/assets/101161d3-bb50-4ef0-b561-be461cb155af)

<p>La declaración de una variable como const permite asegurarse de que su valor no será modificado por el programa, excepto en el momento de su declaración, en el cual debe asignársele un valor inicial. Así, si declaramos la siguiente variable:</p>
<p>const int x=237;</p>
<p>Cualquier intento posterior de modificar el valor de x, tal como x=x+5;, producirá un error en tiempo de compilación.</p>
<p> La declaración de una variable como volatile, indica al compilador que dicha variable puede modificarse por un proceso externo al propio programa (tal como la hora del sistema), y por ello, que no trate de optimizar dicha variable suponiéndole un valor constante, etc. Ello fuerza a que cada vez que se usa la variable, se realice una comprobación de su valor.<br>
Los modificadores const y volatile pueden usarse de forma conjunta en ciertos casos, por lo cual no son excluyentes el uno del otro. Ello es posible si se declara una variable que actualizara el reloj del sistema, (proceso externo al programa), y que no queremos pueda modificarse en el interior del programa. Por ello, <br> podremos declarar:</p>
<p>volatile const unsigned long int hora;</p>

<h3>2.3 - Declaración de variables y alcance.</h3>
<p>En C, las variables pueden ser declaradas en cuatro lugares del módulo del
programa:</p>
<p>• Fuera de todas las funciones del programa, son las llamadas variables globales,
accesibles desde cualquier parte del programa.<br><br> 
•Dentro de una función, son las llamadas variables locales, accesibles tan solo por la función en las que se declaran.<br><br>
• Como parámetros a la función, accesibles de igual forma que si se declararan
dentro de la función.<br><br>
• Dentro de un bloque de código del programa, accesible tan solo dentro del
bloque donde se declara. Esta forma de declaración puede interpretarse como
una variable local del bloque donde se declara.</p>
<p>Para un mejor comprensión, veamos un pequeño programa de C con variables
declaradas de las cuatro formas posibles:</p>

![image](https://github.com/user-attachments/assets/0cb441eb-8936-43f0-b387-c071c03a7174)

<h4>2.4 - Especificadores de almacenamiento de los tipos de
datos.</h4>

<p>Una vez explicada la declaración de variables y su alcance, vamos a proceder a explicar como es posible modificar el alcance del almacenamiento de los datos. Ello es posible realizarlo mediante los especificadores de almacenamiento. Existen cuatro especificadores de almacenamiento. Estos especificadores de almacenamiento, cuando se usan, deben preceder a la declaración del tipo de dato de la variable. Estos especificadores de almacenamiento son:</p>

![image](https://github.com/user-attachments/assets/2089c6a1-0ffa-4dd5-a500-2ff9763bbaa5)

<p>El especificador auto se usa para declarar que una variable local existesolamente mientras estemos dentro de la subrutina o bloque de programa donde se
declara, pero, dado que por defecto toda variable local es auto, no suele usarse.<br><br>El especificador extern se usa en el desarrollo de programas compuestos por
varios módulos. El modificador extern se usa sobre las variables globales del módulo, de forma que si una variable global se declara como extern, el compilador no crea un almacenamiento para ella en memoria, sino que, tan solo tiene en cuenta que dicha variable ya ha sido declarada en otro modulo del programa y es del tipo de dato que se indica.<br><br>
El especificador static actúa según el alcance de la variable:<br><br>
• Para variables locales, el especificador static indica que dicha variable local debe almacenarse de forma permanente en memoria, tal y como si fuera una
variable global, pero su alcance será el que correspondería a una variable local declarada en la subrutina o bloque. El principal efecto que provoca la
declaración como static de una variable local es el hecho de que la variable conserva su valor entre llamadas a la función.<br><br>
• Para variables globales, el especificador static indica que dicha variable global
es local al módulo del programa donde se declara, y, por tanto, no será
conocida por ningún otro módulo del programa.<br><br>
El especificador register se aplica solo a variables locales de tipo char e int. Dicho especificador indica al compilador que, caso de ser posible, mantenga esa
variable en un registro de la CPU y no cree por ello una variable en la memoria. Se pueden declarar como register cuantas variables se deseen, pues el compilador ignorara dicha declaración caso de no poder ser satisfecha. El uso de variables con especificador de almacenamiento register permite colocar en registros de la CPU
variables muy frecuentemente usadas, tales como contadores de bucles, etc.<br><br>
Algunos ejemplos de uso de los especificadores de almacenamiento son:<br>
<pre> register unsigned int a;<br>
static float b;<br>
extern int c;<br>
static const unsigned long int d;</pre></p>
