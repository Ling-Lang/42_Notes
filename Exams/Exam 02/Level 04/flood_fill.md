```c
void ft_fill(char **arr, t_point size, t_point pos, char to_fill)

{

    if(pos.y < 0 || pos.y >= size.y || pos.x < 0 || pos.x >= size.x || arr[pos.y][pos.x] != to_fill)

        return;

    arr[pos.y][pos.x] = 'F';

  

    ft_fill(arr, size, (t_point){pos.x - 1, pos.y}, to_fill);

    ft_fill(arr, size, (t_point){pos.x + 1, pos.y}, to_fill);

    ft_fill(arr, size, (t_point){pos.x, pos.y - 1}, to_fill);

    ft_fill(arr, size, (t_point){pos.x, pos.y + 1}, to_fill);

}
```

As helper function.