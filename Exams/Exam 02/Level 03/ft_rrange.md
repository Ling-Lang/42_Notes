```c
#include <stdlib.h>

int *ft_rrange(int start, int end)

{

int *res;

int i = 0;

int len = end - start + 1;

if(start > end)

return(ft_rrange(end, start));

res = (int *)malloc(sizeof(int) * len);

if(res)

{

while(i < len)

{

res[i] = end;

end--;

i++;

}

}

return res;

}
```