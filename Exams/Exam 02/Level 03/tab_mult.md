```c
#include <unistd.h>

  

int ft_atoi(char *str)

{

int n = 0;

int i = 0;

while(str[i] != '\0')

{

n = n * 10;

n = n + str[i] - '0';

i++;

}

return n;

}

void ft_putnbr(int n)

{

char *set = "0123456789";

if(n >= 10)

ft_putnbr(n / 10);

write(1, &set[n % 10], 1);

}

  

int main(int argc, char **argv)

{

if(argc == 2)

{

int n = ft_atoi(argv[1]);

int i = 1;

while(i <= 9)

{

ft_putnbr(i);

write(1, " x ", 3);

ft_putnbr(n);

write(1, " = ", 3);

ft_putnbr(i * n);

write(1, "\n", 1);

i++;

}

}

else

write(1, "\n", 1);

}
```