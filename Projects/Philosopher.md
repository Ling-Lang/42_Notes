https://github.com/Ling-Lang/42_philosopher.git

```c
typedef struct s_philo

{

size_t num;

size_t last_meal;

size_t is_eating;

size_t limit;

size_t lfork;

size_t rfork;

struct s_data *data;

} t_philo;

typedef struct s_data

{

size_t time_to_eat;

size_t time_to_die;

size_t time_to_sleep;

size_t food;

size_t completed;

size_t num_of_philo;

t_philo *philo;

pthread_mutex_t prints;

pthread_mutex_t forks;

pthread_mutex_t death;

} t_data;
```

size_t because I don't know the upper limit of the stuff and it's unsigned
t_data in philo because we want them to know how many meals are left and stuff?

- `instance` is included in each `philo` struct  to provide shared access to simulation-wide data and resources, facilitating coordinated actions without enabling direct communication among philosophers.