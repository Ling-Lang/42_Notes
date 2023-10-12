```c
#include <stdio.h>

#include <stdlib.h>

  

char *ft_strncpy(char *src, char *dest, int len)

{

int i = 0;

while(i < len && src[i] != '\0')

{

dest[i] = src[i];

i++;

}

dest[i] = '\0';

return(dest);

}

int ft_word_count(char *str)

{

int i = 0;

int wc = 0;

while(str[i])

{

while(str[i] && (str[i] == ' ' || str[i] == '\t' || str[i] == '\n'))

i++;

if(str[i])

wc++;

while(str[i] && str[i] != ' ' && str[i] != '\t' && str[i] != '\n')

i++;

}

return wc;

}

char **ft_split(char *str)

{

int i =0;

int j = 0;

int k = 0;

int word_count = ft_word_count(str);

// Allocate by the ammount of words plus 1

char **res = (char **)malloc(sizeof(char *) * (word_count + 1));

while(str[i])

{

// jump to start of the word

while(str[i] != '\0' &&(str[i] == ' ' || str[i] == '\t' || str[i] == '\n'))

i++;

j = i;

while(str[i] != '\0' && str[i] != ' ' && str[i] != '\t' && str[i] != '\n')

i++;

if(i > j)

{

res[k] = (char *)malloc(sizeof(char) * ((i - j) + 1));

ft_strncpy(&str[j], res[k], i - j);

k++;

}

}

res[k] = NULL;

return res;

}
```
