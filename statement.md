# description: 
 "An aggregate is an array or a class with no user-declared constructors, no private or protected non-static data members, no base classes, and no virtual functions."  Aggregates can be initialized by "brace-enclosed, comma separated list of initializer-clauses for the members of the aggregate, written in increasing subscript or member order."  Static data members are skipped during this type of initialization so 3.14 initializes d and not sd in this example  "If there are fewer initializers in the list than there are members in the aggregate, then each member not explicitly initialized shall be value-initialized". So in this example i is value-initialized to 0.

```C++ runnable
#include <iostream>

class Foo
{
public:

  char c;
  static double sd;
  double d;
  int i;
};

int main(int argc, char** argv) 
{ 
  Foo f = { 72, 3.14 };

  std::cout << f.c + f.d + f.i << std::endl;

  return 0; 
}
