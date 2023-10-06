```c
#include <stdlib.h>

#include <stdio.h>

  

int main(int argc, char **argv)

{

if(argc == 3)

{

int i = 1;

int n1 = atoi(argv[1]);

int n2 = atoi(argv[2]);

int tmp;

if(n1 > n2)

{

while(i <= n2)

{

if(n1 % i == 0 && n2 % i == 0)

tmp = i;

i++;

}

}

else

{

while(i <= n1)

{

if(n1 % i == 0 && n2 % i == 0)

tmp = i;

i++;

}

}

printf("%d", tmp);

}

printf("\n");

}
```

if(n1 % i ==0 && n2 % i == 0)
	tmp = i
	