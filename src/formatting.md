# Formatting

The Nilstrieb C Style Guide Edition 2 mostly follows the principle of maximal readability.
Code, especially C code, is mostly read (by security researchers to find the vulnerabilities),
and therefore readability comes before writability.

## Control flow

Never use braces with `if`/`while`/`do`/`for` statements as they introduce clutter. If your
body cannot fit into a single line, make a new function instead.

```c
   #include<stdio.h>

   void if_bdy() {
      printf("Hello, ");
      printf("World!");
   }
   
   void foo() {
      if (true)
         if_bdy();
      else
         printf("True was false!");
   }
```

## Identation

C code must be indented with 3 spaces. The top-level should be indented as well.

```c
   #include<stdio.h>

   int main() {}
```
