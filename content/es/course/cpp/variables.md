---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Variables"
linktitle: "Variables"
date: 2023-01-04T11:45:24+01:00
type: book
summary: ""
---

## Clase en vídeo

{{< youtube 74CfcfweaC0 >}}

## Ejercicios

### Ejercicio 1

Escribe las sentencias que realizan las acciones descritas:

- Crea una variable llamada `x`, de tipo `int`, y con valor `9`.
  {{< spoiler text="Solución" >}}
  ```C++
  int x {9}; // También: int x = 9;
  ```
  {{< /spoiler >}}
- Crea una variable llamada `e`, de tipo `double`, y con valor `2.718`.
  {{< spoiler text="Solución" >}}
  ```C++
  double e {2.718}; // También: double e = 2.718;
  ```
  {{< /spoiler >}}
- Crea una variable de tipo `char`, con nombre `z` y valor inicial `'z'`.
  {{< spoiler text="Solución" >}}
  ```C++
  char z {'z'}; // También: char z = 'z';
  ```
  {{< /spoiler >}}
- Crea una variable de tipo `string` llamada `s` cuyo valor sea `"hola"`.
  {{< spoiler text="Solución" >}}
  ```C++
  string s {"hola"}; // También: string s = "hola";
  ```
  {{< /spoiler >}}

### Ejercicio 2

Corrige los errores:

```C++
#include <iostream>
#include <string>

using namespace std;

int main()
{
    n {2};
    double pi {3,14};
    char a {"a"};
    string s ["hola"];
    cout << n << pi << a << s << "\n";
}
```

### Ejercicio 3

Escribe en C++:

- Cambial el valor de `x` a `1`.
  {{< spoiler text="Solución" >}}
  ```C++
  x = 1;
  ```
  {{< /spoiler >}}
- Almacena el valor `H` en la variable `letter`.
  {{< spoiler text="Solución" >}}
  ```C++
  letter = 'H';
  ```
  {{< /spoiler >}}
- Crea una variable `uno`, de tipo `int`, y con valor `1`.
  {{< spoiler text="Solución" >}}
  ```C++
  int uno {1}; // También: int uno = 1;
  ```
  {{< /spoiler >}}
- Cambia el valor de `uno` a `2`.`
  {{< spoiler text="Solución" >}}
  ```C++
  uno = 2;
  ```
  {{< /spoiler >}}

### Ejercicio 4

Corrige los errores:

```C++
#include <iostream>
#include <string>

using namespace std;

int main()
{
    string saludo {"hola"}
    cout << saludo << "\n";
    saludo = 'hello';
    cout << saludo << "\n";
    saludo = {"buenas tardes"};
    cout << saludo << "\n";
}
```

### Ejercicio 5

Escribe en C++:

- Crea una variable llamada `best_climber`, de tipo `string`, con valor inicial `Honnold`.
  {{< spoiler text="Solución" >}}
  ```C++
  string best_climber {"Honnold"}; // También: string best_climber = "Honnold";
  ```
  {{< /spoiler >}}
- Escribe en el terminal el valor almacenado en `best_climber`.
  {{< spoiler text="Solución" >}}
  ```C++
  cout << best_climber;
  ```
  {{< /spoiler >}}
- Almacena en `best_climber` la palabra escrita por el usuario en el terminal.
  {{< spoiler text="Solución" >}}
  ```C++
  cin >> best_climber;
  ```
  {{< /spoiler >}}
- Cambia el valor de `best_climber` a `Ginés`.
  {{< spoiler text="Solución" >}}
  ```C++
  best_climber = "Ginés";
  ```
  {{< /spoiler >}}

### Ejercicio 6

Corrige los errores:

```C++
#include <iostream>
#include <cmath>

using namespace std;

int main()
{
    double pi {3,14};
    cout << 'Radio de la esfera? ';
    cin >> radio;
    cout << "Volumen = " << 4 * pi * pow(radio, 3) / 3 << "\n"
}
```

### Ejercicio 7

Escribe un programa, traduciendo cada línea a una sentencia en C++:

```C++
#include "ticlib.h"

using namespace std;

int main()
{
    // Envía a la consola el mensaje: "Calculadora de triángulos\n"
    // Envía a la consola el mensaje: "Escribe la base: "
    // Crea una variable de tipo double llamada base con valor inicial 0.0
    // Lee de la consola un número decimal y guárdalo en la variable base
    // Envía a la consola el mensaje: "Escribe la altura: "
    // Crea una variable de tipo double llamada altura con valor inicial 0.0
    // Lee de la consola un número decimal y guárdalo en la variable altura
    // Envía a la consola el mensaje "El área del triángulo es: "
    // Envía a la consola el resultado de la operación base * altura / 2
}
```

### Ejercicio 8

Escribe un programa que calcule las soluciones de una ecuación de segundo grado (como, {{< math >}}$ax^2 + bx + c = 0$ {{< /math >}}). El programa debe pedir al usuario los coeficientes de la ecuación ({{< math >}}$a${{< /math >}}, {{< math >}}$b${{< /math >}} and {{< math >}}$c${{< /math >}}), y mostrar las dos soluciones de la ecuación.

Recordatorio: las soluciones de una ecuación de segundo grado
{{< math >}}$$ax^2+bx+c=0$${{< /math >}}
vienen dadas por:
{{< math >}}$$x=\dfrac{-b \pm \sqrt{b^2 - 4ac}}{2a}$${{< /math >}}

Por ejemplo, si el usuario escribe:

```markdown
1 -5 6
```

La salida del programa será:

```markdown
2 3
```

## Ejercicios avanzados

### Ejercicio 9

Colores en la consola.

En la consola solo podemos escribir texto, pero podemos escribir texto con colores. Para ello, tenemos que enviar a la consola unos códigos (caracteres) que la consola interpreta como una orden para cambiar el color del texto. Si queremos volver al color anterior, tenemos que enviar otra secuencia de caracteres.

Por ejemplo:

```C++
#include "ticlib.h"

using namespace std;

int main()
{
  cout << "Este texto ";
  cout << "\033[31m"; // Secuencia que cambia el texto a color rojo
  cout << "en rojo ";
  cout << "\033[0m"; // Secuencia que restablece el color del texto al original
  cout << "es un ejemplo.\n";
}
```

Las secuencias de cambio de color siempre empiezan con `\033[`, y terminan con `m`. En medio hay que escribir el código del color.

Estos son los códigos de los colores permitidos:

| Color    | Código |
|-------- |------ |
| rojo     | 31     |
| verde    | 32     |
| azul     | 34     |
| amarillo | 33     |
| magenta  | 35     |
| cian     | 36     |

También se pueden incluir otros códigos que *formatean* el texto (negrita, subrayado&#x2026;):

| Formato   | Código |
|--------- |------ |
| Negrita   | 1      |
| Subrayado | 4      |
| Invertido | 7      |
| Normal    | 0      |

Para enviar dos códigos a la vez, se separan con `;`. Por ejemplo:

```C++
#include "ticlib.h"

using namespace std;

int main()
{
cout << "Este texto ";
cout << "\033[4;31m"; // Secuencia que cambia el texto a subrayado (4) y color rojo (31)
cout << "en rojo y subrayado";
cout << "\033[0m"; // Secuencia que restablece el color del texto al original
cout << " es un ejemplo.\n";
}
```

Escribe un programa que escriba en la consola una lista de colores, de modo que el nombre de cada color esté escrito en el color correspondiente:

```bash
rojo
verde
azul
amarillo
magenta
cian
```

### Ejercicio 10

Leer textos de la consola.

Para representar un texto utilizamos el tipo de datos `string` (también podemos utilizar `char[]`).

Para leer un texto de la consola y guardarlo en una variable, usamos una *sentencia de entrada*:

```C++
string texto;
cin >> texto;
```

Sin embargo, esa sentencia de entrada no funciona como podríamos esperar. Para comprobarlo, escribe el siguiente programa:

```C++
#include "ticlib.h"

using namespace std;

int main()
{
string s;
cout << "Escribe un texto: ";
cin >> s;
cout << "Este es tu texto: " << s << "\n";
}
```

Ejecútalo, y escribe `Esto es una prueba` para ver el resultado. ¿Qué ves en la consola? Algo así:

```bash
Escribe un texto: Esto es una prueba
Este es tu texto: Esto
```

Solo se escribe la primera palabra. ¿Qué ha pasado con el resto de lo que hemos escrito? La respuesta es que la sentencia `cin >> s;` solo guarda en `s` la primera palabra que se escriba en la consola (es decir, hasta encontrar el primer espacio en blanco).

Entonces, ¿cómo podemos escribir un texto formado por varias palabras y guardarlo en una variable de tipo `string`?

La solución es usar otra sentencia distinta para leer textos de la consola. La sentencia es esta:

```C++
getline(cin, s); // Lee una línea entera de la consola y la guarda en s
```

Prueba a sustituir la sentencia `cin >> s;` por `getline(cin, s);` en el programa anterior, y vuelve a probarlo. Ahora sí verás el texto completo.

Esto es una pequeña desventaja de `cin >> s;`. Pero puede ser útil. Por ejemplo, si quieres que un usuario escriba su nombre y apellidos, podrías escribir un programa como este:

```C++
#include "ticlib.h"

using namespace std;

int main()
{
    string nombre;
    string apellido1;
    string apellido2;
    cout << "Escriba su nombre completo (nombre apellido1 apellido2): ";
    cin >> nombre; // Lee la primera palabra escrita (el nombre)
    cin >> apellido1; // Lee la segunda palabra escrita (el primer apellido)
    cin >> apellido2; // Lee la tercera palabra escrita (el segundo apellido)
    cout << "Nombre: " << apellido1 << " " << apellido2 << ", " << nombre << "\n";
}
```

Escribe un programa que permita al usuario escribir dos líneas de texto, y luego muestre las líneas en orden inverso.

Por ejemplo, si el usuario escribe:
```markdown
Primera línea
Segunda línea
```
el programa generará esta salida en el terminal:
```markdown
Segunda línea
Primera línea
```

### Ejercicio 10

El operador `>>` se llama *operador de extracción* porque la operación que realiza es la extracción de un dato de cierto tipo de un dispositivo de entrada. Eso significa que se extrae una secuencia de caracteres que sea interpretable como un dato del tipo que se quiere extraer, y se realiza la conversión de dicha secuencia a un valor del tipo extraído. La extracción se detiene cuando se encuentra un carácter *separador* (espacio en blanco, salto de línea,...), o cuando se encuentra un carácter que haría que la secuencia no fuera interpretable como un valor del tipo extraído.

Ya hemos visto que:

```C++
string s;
cin >> s;
```

extrae caracteres hasta el primer espacio en blanco o salto de línea (cualquier carácter puede formar parte de un valor de tipo `string`).

Otro ejemplo:

```C++
int x;
cin >> x;
```

Si la entrada es `123a`, el valor extraído será `123`.

Otra característica del operador de extracción, `>>`, es que se puede *concatenar*:

```C++
int x;
int y;
int z;
cin >> x >> y >> z;
```

Si la entrada es `1 2 3`, se almacenarán los siguientes valores: en `x`, `1`; en `y`, `2`; y en `z`, `3`.

Escribe el programa del ejercicio 8, utilizando una única sentencia `cin` para obtener los coeficientes.

