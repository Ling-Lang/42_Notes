This is the first project to the [[Core curriculum]].
### Todo

* ft_itoa
* ft_memcmp
* ft_split
* ~~ft_strchr~~
* ~~ft_strtrim~~
* ft_substr

---
## Function Notes
### Atoi

Convert String to int [Atoi Manpage](https://man7.org/linux/man-pages/man3/atoi.3.html)

```C
while (str[i] == ' ' || str[i] == '\t' || str[i] == '\n'
|| str[i] == '\r' || str[i] == '\v' || str[i] == '\f')
{
i++;
}
```
Check for special Character or <`Space`>  and skip over them

```c
if (str[i] == '-' || str[i] == '+')
{
sign = 1 - 2 * (str[i++] == '-');
}
```
Check if Negative or Positive number

```c
while (str[i] >= '0' && str[i] <= '9')
{
check_limit(base, str, i, sign);
base = 10 * base + (str[i++] - '0');
}
```
Convert string to actual number with *MAGIC* actually no just baic ascii conversion

```c
static int check_limit(int base, char *str, int i, int sign)
{
int max;
int min;

max = 2147483647;
min = -2147483648;
if (base > max / 10 || (base == max / 10 && str[i] - '0' > '7'))
{
if (sign == 1)
{
return (max);
}
else
return (min);
}
return (0);
}
```
How stupid you are the function name says it all

---
