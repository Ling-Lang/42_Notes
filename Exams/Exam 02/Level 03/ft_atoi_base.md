```c
int is_blank(char c)

{

if (c <= 32)

return (1);

return (0);

}

  

int isvalid(char c, int base)

{

char digits[17] = "0123456789abcdef";

char digits2[17] = "0123456789ABCDEF";

  

while (base--)

if (digits[base] == c || digits2[base] == c)

return (1);

return (0);

}

int value_of(char c)

{

if (c >= '0' && c <= '9')

return (c - '0');

else if (c >= 'a' && c <= 'f')

return (c - 'a' + 10);

else if (c >= 'A' && c <= 'F')

return (c - 'A' + 10);

return (0);

}

  

int ft_atoi_base(const char *str, int str_base)

{

int result;

int sign = 1;

int i = 0;

result = 0;

while (is_blank(str[i]))

i++;

if(str[i] == '-' || str[i] == '+')

{

if(str[i] == '-')

sign = -1;

i++;

}

while (isvalid(str[i], str_base))

{

result = result * str_base;

result = result + value_of(str[i]);

i++;

}

return (result * sign);

}
```


First skip unprintbles

then check if - or +
then while(str\[i] is valid)
{
res \*=  str_base
res = res + value(str\[i])
i++;
}


value == c - 'A' + 10;
if with letters 
else
c - '0'