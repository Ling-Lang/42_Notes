```c
#include <stdlib.h>

#include <stdio.h>

  

int main(int argc, char **argv)

{

if(argc == 2)

{

int n = atoi(argv[1]);

int i = 1;

if(n == 1)

printf("1");

while(n >= i)

{

i++;

if(n % i == 0)

{

printf("%d", i);

if(n == i)

break;

printf("*");

n /= i;

i = 1;

}

}

}

printf("\n");

}
```

