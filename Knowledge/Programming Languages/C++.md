# Prequisites

# References
C++ Primer
Effective Modern C++
Exceptional C++
C++ Templates: The Complete Guide
Modern C++ Design
C++ Template Metaprogramming
C++ Concurrency in Action
Large Scale C++


# Basics
Hello World:
```
#include <iostream>
int main() {
  std::cout << "Hello world" << std::endl;
}
```

function:
```
// b is a default value
int multiply(int a, int b = 1) {
  return a * b;
}
```

common primitive data types:
* char
* int 
* float
* double

other data types:
* std::string
* vector<some_type>

iteration :
```
for (auto i : my_vector) {
  cout << i << " ";
}
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
while(true) {
  print("x");
} // print x forever
```

Pointers can point to different locations in memory, including pointing to functions.

# Classes

```
class Account {
public:
  void calculate();
private:
  std::string owner;
};
```

There are default constructors and destructors.  `virtual` works well with interfaces.  `friend` allows another class to access private members.

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

`auto` lets the compiler assume the type.

# Helpful Tips

Use smart pointers to help forget about memory management.

When something is copied, a copy of the object is made in memory.  When something is moved, a new variable is referring to the object which leaves the old variable in a undefined state.

templates + generics

