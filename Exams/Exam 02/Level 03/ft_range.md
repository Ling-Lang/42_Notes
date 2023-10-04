```c
#include <stdlib.h>

int     *ft_range(int start, int end)

{

    int size = abs((end - start)) + 1;

    int *arr = (int *)malloc(sizeof(int) * size);

    int i = 0;

    while(i < size)

    {

        if(start < end)

        {

            arr[i] = start;

            start++;

            i++;

        }

        else

        {

            arr[i] = start;

            start--;

            i++;

        }

    }

    return arr;

}
```

len = abs((start - end) ) + 1;