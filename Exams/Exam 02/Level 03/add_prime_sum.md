```c
int is_prime(int n)
{
	int i = 2;
	if(n <= 1)
		return 0;
	while(i * i <= n)
	{
		if(n % i == 0)
			return 0;
		i++;
	}
	return 1;
}
```

Rest is ez