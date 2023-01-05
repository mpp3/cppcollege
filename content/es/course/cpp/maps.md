+++
title = "maps"
author = ["Manuel Pérez"]
date = 2023-01-04
draft = false
type = "book"
+++

## Clase en vídeo {#clase-en-vídeo}


## Notas {#notas}


### Qué es un mapa {#qué-es-un-mapa}

Se le llama también _array asociativo_. En otros lenguajes, una estructura parecida se llama _diccionario_, o _tabla hash_.

Es un conjunto de parejas de datos, en las que el primer dato de cada pareja es de un cierto tipo, K, y el segundo dato de cada pareja es de cierto tipo, V.

Al primer dato de cada pareja se le suele llamar, _clave_, y al segundo, _valor_.

Los mapas permiten crear asociaciones _clave_-&gt;/valor/. De modo que, conociendo una _clave_, podemos conocer el _valor_ asociado a esa clave.

Existen varias versiones de este tipo de datos en C++. Nosotros solo utilizaremos la que se llama `map`, en la cual:

-   las claves no pueden estar repetidas (no puede haber dos parejas con la misma clave);
-   las claves deben ser _ordenables_ (es decir, debe existir un operador `<` definido para comparar dos valores de tipo K);
-   las parejas se guardan ordenadas según su clave en orden ascendente.

Por ejemplo, si quisiéramos que un programa manejase una tabla de ciudades y sus poblaciones, solo con vectores, podríamos hacer lo siguiente:

```C++
vector<string> cities {"Madrid", "London", "Moscow", "Istanbul"};
vector<int> population {3305408, 8799800, 12632409, 15840900};
```

Ahora, si queremos saber la población de una ciudad, primero tenemos que averiguar cuál es la posición de esa ciudad en las listas, y luego extraer el elemento del vector de poblaciones que está en esa posición.

```C++
cout << "Escriba el nombre de una ciudad: ";
string ciudad;
cin >> ciudad;
int pos {0};
while (cities[pos] != ciudad) {
    pos++;
}
cout << "La población de " << ciudad << " es " << population[pos];
```

Si quisiéramos añadir una ciudad deberemos tener cuidado de añadir inmediatamente su población. Lo mismo al eliminar una ciudad. Es fundamental conservar la sincronización entre las dos listas.

Vamos a ver cómo, gracias a los mapas, podemos relacionar directamente las ciudades con sus poblaciones, sin necesidad de recurrir a las posiciones. Eso hará mucho más sencillos estos programas.


### Cómo se define un mapa {#cómo-se-define-un-mapa}

Para definir un mapa tenemos que crear una variable de tipo `map<K, V>`, donde `K` es el tipo de datos de las claves, y `V` es el tipo de datos de los valores. El inicializador (entre llaves) es una lista de parejas de datos del tipo `{K, V}`.

Por ejemplo,

```C++
map<string, int> population {
    {"Madrid", 3305408},
    {"London", 8799800},
    {"Moscow", 12632409},
    {"Istanbul", 15840900}
};
```

Obsérvese que la disposición en varias líneas es solo para mejorar la legibilidad: el compilador ignora los espacios en blanco y saltos de línea excepto como separadores.

El orden en que hemos escrito los datos no es el orden en que se almacenarán en el mapa, ya que los datos se guardan ordenados por clave.


### Cómo acceder a los datos de un mapa {#cómo-acceder-a-los-datos-de-un-mapa}

Para obtener el valor asociado a cierta clave, utilizamos el operador _subíndice_, `[]` (el mismo que usábamos en los vectores para seleccionar un elemento a partir de su índice).

Por ejemplo,

```C++
cout << "La población de Madrid es " << population["Madrid"];
```

Dentro de los corchetes podemos utilizar cualquier expresión cuyo valor sea del tipo que tienen las claves del mapa. Por ejemplo,

```C++
cout << "Escriba el nombre de una ciudad: ";
string ciudad;
cin >> ciudad;
cout << "La población de " << ciudad << " es " << population[ciudad];
```

Si no existiera ninguna pareja con esa clave, se crearía automáticamente una pareja con esa clave, y se le pondría como valor el valor inicial por defecto correspondiente al tipo de los valores.


### Cómo modificar, añadir y eliminar datos de un mapa {#cómo-modificar-añadir-y-eliminar-datos-de-un-mapa}

Para modificar un dato (es decir, para cambiar el valor asociado a una clave), usamos el mismo operador _subíndice_, `[]`. Por ejemplo:

```C++
population["Istanbul"] = 10224323;
```

Para añadir un dato, podemos usar el mismo operador _subíndice_. Por ejemplo:

```C++
population["Berlin"] = 3677472;
```

Cuando la clave no existe en el mapa, se crea una pareja nueva con esa clave, y se le asigna el valor indicado. Si la clave ya existiese, lo que haríamos sería modificar el valor asociado a esa clave (como en el ejemplo anterior).

Para eliminar un dato, usamos la función `erase`:

```C++
population.erase("Berlin");
```


### Cómo comprobar si una clave existe en un mapa {#cómo-comprobar-si-una-clave-existe-en-un-mapa}

Para comprobar si hay alguna pareja en el mapa que tenga cierta clave, usamos una función que nos dice cuántas veces aparece una clave en un mapa. Como las claves no pueden estar repetidas, esa función dará como resultado `1`, si la clave está presente en el mapa, o `0`, si la clave no está presente. De modo que podemos usar una sentencia `if` como la siguiente para comprobar si una clave está presente en un mapa:

```C++
if (population.count(ciudad) == 0) {
    cout << "No tenemos la población de " << ciudad;
}
```

Con esto, podríamos mejorar el ejemplo anterior:

```C++
cout << "Escriba el nombre de una ciudad: ";
string ciudad;
cin >> ciudad;
if (population.count(ciudad) != 0) {
    cout << "La población de " << ciudad << " es " << population[ciudad];
}
else {
    cout << "No tenemos la población de " << ciudad;
}
```

En C++20 existe otra función específica para realizar esta comprobación: `contains`. Por ejemplo,

```C++
if (population.contains(ciudad)) {
    cout << "No tenemos la población de " << ciudad;
}
```


### Cómo iterar los elementos de un mapa {#cómo-iterar-los-elementos-de-un-mapa}

_Iterar_ los elementos de un mapa significa realizar alguna operación con todas las parejas del mapa.

Para ello, podemos usar un _bucle for basado en contenedores_:

```C++
cout << "Poblaciones de las mayores capitales europeas:\n";
for (auto elemento : population)
{
    cout << elemento.first << ": " << elemento.second << " habitantes\n";
}
```

En cada iteración de este bucle, la variable `elemento` se irá refiriendo sucesivamente a una pareja distinta del mapa. Para acceder a la clave de dicha pareja usamos `elemento.first`, y para acceder al valor, usamos `elemento.second`.


## Ejercicios de repaso {#ejercicios-de-repaso}


### Ejercicio 1 {#ejercicio-1}

Escribe un programa que muestre en la consola el siguiente mensaje:

```markdown
El carácter de escape en C++ es el carácter llamado "backslash": '\'
```


### Ejercicio 2 {#ejercicio-2}

Escribe un programa que lea del usuario una línea de texto, y luego le pregunte cuántas veces quiere repetirla, y que escriba en la consola dicha línea repetida tantas veces como el usuario le indicó.


### Ejercicio 3 {#ejercicio-3}

Escribe un programa que pregunte al usuario una base de numeración, y luego le pida un carácter, y le diga si el carácter escrito es un dígito válido para esa base de numeración. El programa admitirá como máximo hasta la base 16.

Suponemos que todos los sistemas de numeración utilizan en primer lugar los dígitos del 0 al 9, y luego las letras minúsculas, en orden alfabético. El número de dígitos distintos de cada sistema de numeración es igual a su base. Por ejemplo, el sistema octal (base 8), solo admite los dígitos `0` a `7`, el sistema binario (base 2), los dígitos `0` y `1`, el sistema decimal (base 10), los dígitos `0` a `9`, el sistema hexadecimal (base 16), los dígitos `0` a `9` y las letras de la `a` a la `f`, etc.


### Ejercicio 3 {#ejercicio-3}

Escribe un programa que lea del usuario una lista de números, y luego le indique cuál es la suma y el producto de todos los números escritos. El programa debe comenzar preguntando al usuario cuántos números desea escribir.


### Ejercicio 4 {#ejercicio-4}

Escribe un programa que escriba en el terminal el siguiente menú de opciones:

```markdown
1 Averiguar capital
2 Añadir capital
3 Eliminar capital
4 Ver todas las capitales
5 Salir
```

Luego el programa pedirá al usuario un número, y mostrará en el terminal el texto de la opción elegida, excepto en el caso de que la opción elegida sea 5, momento en que el programa terminará.


## Ejercicios {#ejercicios}


### Ejercicio 5 {#ejercicio-5}

Escribe un programa que cree un mapa con los datos siguientes:

| País      | Capital    |
|-----------|------------|
| Dinamarca | Copenhague |
| Hungría   | Budapest   |
| Francia   | París      |
| Italia    | Roma       |
| Bulgaria  | Sofía      |

Luego, el programa debe pedir el nombre de un país, y escribir en el terminal el nombre de su capital. Si el país escrito por el usuario no está en la lista, el programa se lo indicará así al usuario.


### Ejercicio 6 {#ejercicio-6}

Modifica el programa del ejercicio anterior, para que se muestre al usuario un menú como el del ejercicio 4, y se realicen las acciones indicadas, utilizando el mapa de capitales creado en el ejercicio 5.


### Ejercicio 7 {#ejercicio-7}

Escribe un programa que cree un mapa con los datos siguientes:

| Elemento  | Masa atómica |
|-----------|--------------|
| Hidrógeno | 1.008        |
| Helio     | 4.003        |
| Oxígeno   | 16           |
| Silicio   | 28.085       |
| Potasio   | 39.098       |
| Calcio    | 40.078       |
| Uranio    | 238.029      |

Luego, el programa deberá mostrar un menú con opciones análogas a las de los ejercicios 4 y 6, y realizar las acciones indicadas en el menú, permitiendo consultar la tabla de masas atómicas, añadir elementos, eliminar elementos, mostrar la lista de todos los elementos con sus masas atómicas, y salir del programa.


### Ejercicio 8 {#ejercicio-8}

Escribe un programa que lea un texto del terminal, y cuente cuántas veces aparece repetido cada carácter. Al final, el programa debe mostrar una tabla con todos los caracteres encontrados y el número de veces que ha encontrado cada uno.

Indicación: construye un mapa, en el cada pareja tendrá como clave un carácter, y como valor, el número de repeticiones de ese carácter. El programa deber recorrer el texto leído del terminal, añadiendo o actualizando los datos del mapa.


## Ejercicios avanzados {#ejercicios-avanzados}


### Ejercicio 9 {#ejercicio-9}

Escribe un programa que lea un texto del terminal y detecte si hay palabras repetidas. El programa deberá construir una lista con las palabras repetidas, y, al final, deberá mostrar dicha lista.


## Soluciones en vídeo {#soluciones-en-vídeo}
