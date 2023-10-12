https://github.com/Ling-Lang/42_philosopher.git

first we validate if everyting is a number and the right ammount of args is there
then we allocate the threads and the data structure
then we fill the data
in there we allocate the death_mutex and set  the start_time value to the current time
after that we fill for every philo the data like the time to die eat and sleep.
We check if we have a limited ammount of meals and set the corresponding bool
we assign every philo its id
and set the state to thinking for the beginning

then we initiate the mutexes;
after that we create the thread for the watcher which checks if a philosopher should die and the game should end

then we create the first half of philo threads and start their routine we split this to prevent deadlocks 
then the second half
and then if everything is finished and the sim ends we just join the threads together and destroy the mutexes and free everything.

### Philo routine

by default we think
we check after every iteration if the philos should die eat or sleep

#### ft_should_die

we check if data->is_dead is true if yes we return 1 which stops the simulation
else we continue

#### ft_last_meal

If we have a limited ammount of meals we check if there are any left on the current iteration and if not we return 1 which stops the simulation else we contiune

#### ft_think
we print thinking

#### ft_eat

first we lock the first fork which belongs to the philo then we print then if there are more than 1 philos we lock the next fork wich belongs to the philo next to us
we print again and set the state to eating 
we lock the mealtime and set the tie of the last eaten meal and unlock the mutex then we print and wait for time to eat ammount of time and unlock the mutexes
if only 1 philo we let the fork go and wait until he is dead


## Watcher routine

we check every 500 useconds and check again 

#### ft_die

we check for every philosopher when their last meal was and compare that to the current time we also asign this to time_of_death if this exceeds the threshold of timetodie we set the is_dead flag in data and print that he dies and then we return 1 which stops the simulation
else 
continue

#### ft_stop
if there are unlimited meals we continue if not we check for every philo if they have enough meals if not we return 1 which stops the simulation else we contiune