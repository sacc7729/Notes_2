# Prequisites
N/A

# References
The C Programming Language
C Programming: A Modern Approach
Modern C <- Good book

# Basics
Hello World:
```
#include <stdio.h>
main() {
  printf("hello world\n");
}
```

function:
```
int multiply(int a, int b) {
  return a * b;
}
```

common data types:
* char
* int 
* float
* double

array:
```
int my_array[10];
my_array[0] = 42;
```

control statements:
```
for (int i = 0; i < 10; i++) {
  if (i == 3) {
    printf("divisible by three");
  }
}
```

```
char letter = "m";
switch(letter) {
  case "a":
  case "b":
    printf("a or b");
    break;
  default:
    printf("not a or b");
}
```

```
do {
  print("x");
} while (true);  // print x forever
```

Pointers can point to different locations in memory, including pointing to functions.

# Helpful Keywords

`extern` emphasizes that the variable referes to an external variable:
```
int max;
int min;

main () {
  extern int max; // use the max variable described above
  int min;  // create a new variable min in this scope
}
```

`const` marks as read-only so the compiler can optimize:
```
// promises that x won't change
const int x = 5;
```

`inline` can be used to suggest to the compiler that the call to a fuction shouldn't have the overhead of a function call.  The overhead of calling a function is typically only a few instructions, but if the function is called often then the benefits may add up.
```
inline double average(double a, double b) {
  return (a + b) / 2;
}
```

`static` is used to preserve a value even after it is out of scope.  The variable is not initialized again:
```
int my_function() {
  static int count = 0;
  count++;
  return count;
}

printf(my_function()); // 1
printf(my_function()); // 2
```

`constexpr` suggests to the compiler that the value should be computed at compile-time:
```
constexpr int product(int x, int y) {
  return x * y;
}

int x = product(10, 20);
```
`volatile` means the value can change at any time.  `volatile` is often used in concurrent procedures.
```
volatile int x = 5;
// start another procedure with x concurrently
printf(x); // 5
printf(x); // 8
```

`register` suggest that the variable should be accessed quickly (e.g. may be stored in a register)
```
register int x;
```

preprocessor works with the following:
* `#if`
* `#elif`
* `#endif`
* `#define`
* `#include`

# Containers

enums:
```
enum color {RED, BLUE, GREEN};
```
structs:
```
struct Coordinate {
  int x;
  int y;
}

struct Coordinate my_coordinate;
my_coordinate.x = 10;
my_coordinate.y = 20;
```

A union is a variable can that hold objects of different types and sizes:
```
union Identification {
  char name[];
  int identifications;
}
```

# Memory Management

If you need to define memory dynamically:
```
// some_value only known at run time
my_pointer = malloc(some_value);
// do something with my_pointer
free(my_pointer);
```
Or if you need some memory reserved longer than the lifetime of some block:
```
int* my_function () {
  int *my_pointer = malloc(sizeof(int));
  // do something with my_pointer
  return my_pointer;
}

int *x = my_function();
// do something with x
free(x);
```

# Compilation

A `translation unit` is a source file along with the header files needed for it to compile.

The header files will include the declarations needed for the translation unit to compile.  The linker is in charge of choosing the definition needed across translation units.

# Standard Library

The standard library has useful features.  Don't reinvent the wheel.

# Concurrency
Use `pthrd_create` to create a thread.

`thread_local` implies local to the thread.

# Advanced Tips

Use `restrict` to tell the compiler that the data accessed through a pointer can only be accessed from the pointer.

Use `_Generic` to create generics.  `_Generic` basically acts as a switch for types.

variadic functions take a variable number of arguments:
```
int largest_number(int n, ...) {
  // use va_xxx to access the parameters 
}
```