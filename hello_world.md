# Print hello world on centos7 base machine (x86)
cat helloworld.c
```sh
#include <stdio.h>
int main() {
   // printf() displays the string inside quotation
       printf("Hello, World!");
          return 0;
          }
```
step 1:
```sh
gcc helloworld.c -o helloworld_x86
Note: in the place of helloworld_x86 you can use any name according to your wish
```
step 2:
```sh
./helloworld_x86
```
output:
```sh
Hello, World!
```

