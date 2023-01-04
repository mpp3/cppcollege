---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Variables"
linktitle: "Variables"
date: 2023-01-04T11:45:24+01:00
type: book
summary: ""
---

## Video class

{{< youtube 74CfcfweaC0 >}}

## Exercises

### Exercise 1

Write sentences that perform the actions described:

- Create a variable of type `int`, name `x` and value `9`.
  {{< spoiler text="Solution" >}}
  ```C++
  int x {9}; // Also: int x = 9;
  ```
  {{< /spoiler >}}
- Create a variable of type `double`, with name `e` and value `2.718`.
  {{< spoiler text="Solution" >}}
  ```C++
  double e {2.718}; // Also: double e = 2.718;
  ```
  {{< /spoiler >}}
- Create a variable of type `char` called `z` with initial value `'z'`.
  {{< spoiler text="Solution" >}}
  ```C++
  char z {'z'}; // Also: char z = 'z';
  ```
  {{< /spoiler >}}
- Create a variable of type `string` called `s` with value `"hello"`.
  {{< spoiler text="Solution" >}}
  ```C++
  string s {"hello"}; // Also: string s = "hello";
  ```
  {{< /spoiler >}}

### Exercise 2

Fix the errors:

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

### Exercise 3

Write in C++:

- Change the value of `x` to `1`.
  {{< spoiler text="Solution" >}}
  ```C++
  x = 1;
  ```
  {{< /spoiler >}}
- Store the value `H` in the variable `letter`.
  {{< spoiler text="Solution" >}}
  ```C++
  letter = 'H';
  ```
  {{< /spoiler >}}
- Create a variable of type `int` called `one` with value `1`.
  {{< spoiler text="Solution" >}}
  ```C++
  int one {1}; // Also: int one = 1;
  ```
  {{< /spoiler >}}
- Change the value of `one` to `2`:
  {{< spoiler text="Solution" >}}
  ```C++
  one = 2;
  ```
  {{< /spoiler >}}

### Exercise 4

Fix the errors:

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

### Exercise 5

Write in C++:

- Create a variable called `best_climber`, of type `string`, with initial value `Honnold`.
  {{< spoiler text="Solution" >}}
  ```C++
  string best_climber {"Honnold"}; // Also: string best_climber = "Honnold";
  ```
  {{< /spoiler >}}
- Write to the terminal the value stored in `best_climber`.
  {{< spoiler text="Solution" >}}
  ```C++
  cout << best_climber;
  ```
  {{< /spoiler >}}
- Store in `best_climber` the word written by the user in the terminal.
  {{< spoiler text="Solution" >}}
  ```C++
  cin >> best_climber;
  ```
  {{< /spoiler >}}
- Change the value of `best_climber` to `Ginés`.
  {{< spoiler text="Solution" >}}
  ```C++
  best_climber = "Ginés";
  ```
  {{< /spoiler >}}

### Exercise 6

Fix the errors:

```C++
#include <iostream>
#include <cmath>

using namespace std;

int main()
{
    double pi {3,14};
    cout << 'Sphere radius? ';
    cin >> radius;
    cout << "Volume = " << 4 * pi * pow(radius, 3) / 3 << "\n"
}
```

### Exercise 7

Write a program, translating each line to a C++ sentence:

```C++
#include "ticlib.h"

using namespace std;

int main()
{
    // Write on the terminal the message: "Triangle calculator\n"
    // Write on the terminal the message: "Write the base length: "
    // Create a variable of type 'double' called 'base' and with value 0.0
    // Get a decimal number from the terminal and store it in 'base'
    // Write on the terminal the message: "Write the height: "
    // Create a variable of type 'double' called 'height' and with value 0.0
    // Read from the terminal a decimal number and store it in 'height'
    // Send to the terminal the text "The triangle's area is: "
    // Send to the terminal de result of the operation base * height / 2
}
```

### Exercise 8

Write a program that computes the solutions of a quadratic equation (like, {{< math >}}$ax^2 + bx + c = 0$ {{< /math >}}). The program should ask the user to input the coefficients of the equation ({{< math >}}$a${{< /math >}}, {{< math >}}$b${{< /math >}} and {{< math >}}$c${{< /math >}}), and then it will show the solutions of the equation.

Reminder: the solutions of the quadratic equation, 
{{< math >}}$$ax^2+bx+c=0$${{< /math >}}
are given by
{{< math >}}$$x=\dfrac{-b \pm \sqrt{b^2 - 4ac}}{2a}$${{< /math >}}


## Advanced exercises

### Exercise 9

Colors in the terminal.

A terminal is a text-only device: we can only write text on it. But we can write colorized text. In order to stablish the color of the text, we have to send to the terminal some codes (characters) which are interpreted by the terminal as an order to change the color of the text. If we want to go back to the previous color, we must send another special character sequence.

For example,

```C++
#include "ticlib.h"

using namespace std;

int main()
{
  cout << "This text ";
  cout << "\033[31m"; // Sequence that changes the text color to red
  cout << "in red ";
  cout << "\033[0m"; // Sequence that resets the original color
  cout << "is an example.\n";
}
```

The sequence for changing the color start always with `\033[`, and end with `m`. Between them, we must write the color code.

This are the allowed color codes:

| Color    | Code |
|-------- |------ |
| red     | 31     |
| green    | 32     |
| blue     | 34     |
| yellow | 33     |
| magenta  | 35     |
| cyan     | 36     |

We can also include other codes that change the aspect of the text (bold, underline,...):

| Format   | Code |
|--------- |------ |
| Bold   | 1      |
| Underline | 4      |
| Invert | 7      |
| Normal    | 0      |

We can send two codes *at the same time* (in the same sequence), separating them with `;`. For example:

```C++
#include "ticlib.h"

using namespace std;

int main()
{
cout << "This text ";
cout << "\033[4;31m"; // Sequence that changes the text to underline (4) and color red (31)
cout << "in red and underlined";
cout << "\033[0m"; // Sequence that resets the original color and format
cout << " is an example.\n";
}
```

Write a program that writes in the console a list of colors, with the name of each color in the color it names:

```markdown
red
green
blue
yellow
magenta
cyan
```

### Exercise 10

Reading texts from the console.

To represent texts in C++, we use the type `string` (we can also use the type `char[]`).

For reading a text from the terminal and storing it in a variable, we use an input sentence:

```C++
string text;
cin >> text;
```

How ever, this input sentence does not work as we might expect. Write this program:

```C++
#include <iostream>

using namespace std;

int main()
{
string s;
cout << "Write a text: ";
cin >> s;
cout << "This is your text: " << s << "\n";
}
```

Compile and run the program, and write `This is a test` as input. What do you see in the terminal as output? Something like this:

```markdown
Write a text: This is a test
This is your text: This
```

Only the first word is written as output. What happened to the rest of the input? The answer is that the sentence `cin >> s;` only stores in `s` the first word written in the terminal (i.e., the characters up to the first blank space).

Then, how can we write a text with several words and keep it in a `string` variable?

The solution is to use a different sentence to read texts from the terminal:

```C++
getline(cin, s); // Gets a whole line from the standard input and stores it in s
```

Replace the sentence `cin >> s;` with `getline(cin, s);` in the previous program, and check it again. Now you will see the full text.

Write a program that allows the user to input two lines of text, and then shows the lines in reverse order.

For example, if the user writes:

```markdown
First line
Second line
```

the program will output to the terminal:

```markdown
Second line
First line
```
