---
title: "Output"
date: 2020-01-01T20:52:47+01:00
type: book
weight: 20
---

## Clase en vídeo

{{< youtube u-jeJWcaQHo >}}

## Ejercicios

### Ejercicio 1
Escribe un programa equivalente al siguiente, pero con una única sentencia:

```C++
#include <iostream>

using namespace std;

int main()
{
    cout << "El coseno de 90 grados es: ";
    cout << cos(M_PI/2);
    cout << "\n";
}
```

### Ejercicio 2
Corrige los errores del programa siguiente:
```C++
#include <iostream>

using namespace std;

int main()
{
    // Queremos escribir "programa" entre comillas, pero...
    cout << "Este "programa" es incorrecto\n";
}
```

### Ejercicio 3
Corrige los errores:
```C++
#include <iostream>

using namespace std;

int main()
{
    cout << "El logaritmo decimal de 10 es: " log10(10) \n;
    cout << "El logaritmo decimal de 100 es: " log10(100) "\n";
    cout << "El logaritmo decimal de 1000 es: log10(1000) \n";
}
```
Después de corregir los errores, el programa debería generar la siguiente salida en el terminal:
```markdown
El logaritmo decimal de 10 es: 1
El logaritmo decimal de 100 es: 2
El logaritmo decimal de 1000 es: 3
```

### Ejercicio 4
Escribe un programa que *dibuje* lo siguiente en el terminal:
```markdown
  / _ \
\_\(_)/_/
 _//"\\_
  /   \
```

### Ejercicio 5
Modifica el siguiente programa de modo que produzca la misma salida en el terminal, pero con
una única sentencia:
```C++
#include <iostream>

using namespace std;

int main()
{
    cout << "La raíz cuadrada de 25 es: ";
    cout << sqrt(25);
    cout << "\n";
}
```

### Ejercicio 6
Corrige los errores:
```C++
#include <iostream>

int main()
{
    cout << "El creador de C++ es Bjarne Stroustrup.\n
}
```

### Ejercicio 7

Escribe un programa que escriba esto en el terminal:
```markdown
  /\
 //\\
///\\\
```

### Ejercicio 8
Escribe un programa que escriba lo siguiente en el terminal, pero usando una única sentencia:
```markdown
¡
H
o
l
a
!
```

### Ejercicio 9

Escribe un programa que genere la siguiente salida en el terminal:

```markdown
  __    __    _______  ___      ___        ______        __   __  ___     ______     _______   ___       ________
 /" |  | "\  /"     "||"  |    |"  |      /    " \      |"  |/  \|  "|   /    " \   /"      \ |"  |     |"      "\
(:  (__)  :)(: ______)||  |    ||  |     // ____  \     |'  /    \:  |  // ____  \ |:        |||  |     (.  ___  :)
 \/      \/  \/    |  |:  |    |:  |    /  /    ) :)    |: /'        | /  /    ) :)|_____/   )|:  |     |: \   ) ||
 //  __  \\  // ___)_  \  |___  \  |___(: (____/ //      \//  /\'    |(: (____/ //  //      /  \  |___  (| (___\ ||
(:  (  )  :)(:      "|( \_|:  \( \_|:  \\        /       /   /  \\   | \        /  |:  __   \ ( \_|:  \ |:       :)
 \__|  |__/  \_______) \_______)\_______)\"_____/       |___/    \___|  \"_____/   |__|  \___) \_______)(________/
```

## Ejercicios avanzados:

### Ejercicio 10

El siguiente programa pretende escribir cinco puntos en el terminal, pero con un retardo de un segundo entre ellos. Si lo compilas y ejecutas, verás que no funciona como se esperaba:

```C++
#include <iostream>
#include <thread>


// Este programa utiliza la función 'this_thread::sleep_for',
// que detiene la ejecución durante el tiempo especificado.
// Dicha función se proporciona en la librería estándar 'thread',
// por lo que debemos incluirla.
//
// La cantidad de tiempo se especifica utilizando un prefijo que indica
// la unidad de tiempo utilizada: '1s' signfica 'un segundo'.
// Para poder utilizar ese tipo de sufijos necesitamos declarar el
// espacio de nombres 'std::literals'

using namespace std;
using namespace std::literals

int main()
{
  cout << ".";
  this_thread::sleep_for(1s);
  cout << ".";
  this_thread::sleep_for(1s);
  cout << ".";
  this_thread::sleep_for(1s);
  cout << ".";
  this_thread::sleep_for(1s);
  cout << ".";
}
```

¿Cuál es el comportamiento del programa?

Investiga un poco en qué consiste la operación *flush* en un dispositivo de salida:


https://stackoverflow.com/questions/60052408/c-why-does-this-code-only-work-when-using-n

https://en.cppreference.com/w/cpp/io/manip/flush

Luego, intenta arreglar el programa para que funcione como se pretendía (con un segundo de retardo entre cada punto y el siguiente).

### Ejercicio 11

Cuando escribimos un número decimal en el terminal, ¿cómo decidimos cuántas cifras decimales deben aparecer?

https://stackoverflow.com/questions/4217510/how-to-cout-the-correct-number-of-decimal-places-of-a-double-value

https://en.cppreference.com/w/cpp/io/manip/setprecision

Después de estudiar la información de los enlaces anteriores, modifica el siguiente programa para que imprima en el terminal 10 dígitos después del punto decimal:

```C++
#include <iostream>

using namespace std;

int main()
{
  cout << "La raíz cuadrada de 2 es: " << sqrt(2) << "\n";
}
```

