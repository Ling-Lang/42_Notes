```c
#include <unistd.h>

  

int main(int argc, char **argv)

{

if(argc == 2)

{

int i = 0;

int flag;

while(argv[1][i] == ' ' || argv[1][i] == '\t')

i++;

while(argv[1][i] != '\0')

{

if(argv[1][i] == ' ' || argv[1][i] == '\t')

flag = 1;

if(!(argv[1][i] == ' ' || argv[1][i] == '\t'))

{

if(flag == 1)

write(1, " ", 1);

flag = 0;

write(1, &argv[1][i], 1);

}

i++;

}

}

write(1, "\n", 1);

}
```


`if(str[i] == ' ' || '\t')`
flag = 1

if flag == 1
print ' '