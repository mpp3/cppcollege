---
title: "Output"
date: 2020-01-01T20:52:47+01:00
type: book
weight: 20
---

## Video class

{{< youtube u-jeJWcaQHo >}}

## Exercises

### Exercise 1
Write a program which is equivalent to the next one, but with one only sentence:

```C++
#include <iostream>

using namespace std;

int main()
{
    cout << "The cosine of 90 degrees is: ";
    cout << cos(M_PI/2);
    cout << "\n";
}
```

### Exercise 2
Fix this program:
```C++
#include <iostream>

using namespace std;

int main()
{
    // We want to write "program" in quotes, but...
    cout << "This "program" is wrong\n";
}
```

### Exercise 3
Fix the errors:
```C++
#include <iostream>

using namespace std;

int main()
{
    cout << "The decimal logarithm of 10 is: " log10(10) \n;
    cout << "The decimal logarithm of 100 is: " log10(100) "\n";
    cout << "The decimal logarithm of 1000 is:  log10(1000) \n";
}
```
After fixing the errors, the program should output this text to the terminal:
```bash
The decimal logarithm of 10 is: 1
The decimal logarithm of 100 is: 2
The decimal logarithm of 100 is: 3
```

### Exercise 4
Write a program that outputs this to the terminal:
```markdown
  / _ \
\_\(_)/_/
 _//"\\_
  /   \
```
Modify the next program in such a way that it produces the same output to the terminal, but with one sentence only:
```C++
#include <iostream>

using namespace std;

int main()
{
    cout << "The square root of 25 is ";
    cout << sqrt(25);
    cout << "\n";
}
```

### Exercise 5
Fix the errors:
```C++
#include <iostream>

int main()
{
    cout << "The creator of C++ is Bjarne Stroustrup.\n
}
```

### Exercise 6

Write a program that writes this to the terminal:
```markdown
  /\
 //\\
///\\\
```

### Exercise 3
Write a program that writes this to the terminal, but with one sentence only:
```markdown
H
e
l
l
o
!
```

### Exercise 3

Write a program that writes this to the terminal:

```markdown
  __    __    _______  ___      ___        ______        __   __  ___     ______     _______   ___       ________
 /" |  | "\  /"     "||"  |    |"  |      /    " \      |"  |/  \|  "|   /    " \   /"      \ |"  |     |"      "\
(:  (__)  :)(: ______)||  |    ||  |     // ____  \     |'  /    \:  |  // ____  \ |:        |||  |     (.  ___  :)
 \/      \/  \/    |  |:  |    |:  |    /  /    ) :)    |: /'        | /  /    ) :)|_____/   )|:  |     |: \   ) ||
 //  __  \\  // ___)_  \  |___  \  |___(: (____/ //      \//  /\'    |(: (____/ //  //      /  \  |___  (| (___\ ||
(:  (  )  :)(:      "|( \_|:  \( \_|:  \\        /       /   /  \\   | \        /  |:  __   \ ( \_|:  \ |:       :)
 \__|  |__/  \_______) \_______)\_______)\"_____/       |___/    \___|  \"_____/   |__|  \___) \_______)(________/
```

## Advanced exercises:

### Exercise 10

The next program is trying to write five dots on the terminal, but with a delay of one second between them. If you compile and run the program, you will find that it doesn't work as expected:

```C++
#include <iostream>
#include <thread>

// This program uses the function 'this_thread::sleep_for',
// which makes the execution stop for the specified amount of time.
// This function is provided by the 'thread' standard library,
// which must be, therefore, included.
//
// The time is specified using a suffix which indicates the time unit used:
// '1s' means 'one second'. To be able to use this kind of suffixes,
// we need to declare the namespace std::literals

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

What's the behaviour of the program?

Investigate a little what *flushing* the output means:

https://stackoverflow.com/questions/60052408/c-why-does-this-code-only-work-when-using-n

https://en.cppreference.com/w/cpp/io/manip/flush

Then, try and fix the program so that it works as expected (with a one second delay between the output of every dot).

### Exercise 11

When you write decimal numbers to the terminal, how can you decide how many decimal digits to print?

https://stackoverflow.com/questions/4217510/how-to-cout-the-correct-number-of-decimal-places-of-a-double-value

https://en.cppreference.com/w/cpp/io/manip/setprecision

Modify the next program so that it prints 10 digits after the decimal point:

```C++
#include <iostream>

using namespace std;

int main()
{
  cout << "The square root of 2 is: " << sqrt(2) << "\n";
}
```

