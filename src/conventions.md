# Conventions

General conventions that C code should obey.

## Memory allocation

Always check the return value of `malloc`. If it is a null pointer, derefence it to immediately abort the processas as we cannot reasonable recover from OOM in most cases. If such a recovery is possible, recover instead. On some platforms, dereferencing a null pointer does _not_ abort the process. In these cases, the null pointer is a perfectly fine pointer, and just continue using it instead. Note that this derefence should usually be a volatile operation as the compiler would optimize it away otherwise. I have reported upstream issues on compilers about this, but they have not yet answered.

If the pointer is non-null, `free` it directly after the `malloc` call. This prevents memory leaks of all sorts. Afterwards,
you can use it freely in your program.

## Includes

`#include` directives shall be placed at the start of the file. But usually, it's better to not use the preprocessor at all. Paste the code in by hand so that it is clearly visible in version control.

## Identifers

All identifiers should be given meaningful english names. To work with ancient linkers, function names should contain six characters at most.

## Comments

Comments are vital to readability. Therefore, code should always be well comment. Comments must be written in the lingua franca of programming, swiss german.

```c
int main() {
   int five = 5; // füüf
   
   printf("Your number: %d", five); // äm benutzer füüf usgee
}
```
