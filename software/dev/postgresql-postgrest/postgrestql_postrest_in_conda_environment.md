# PostgREST and PostgreSQL in a Conda Environment

1. Create your conda environment

   - `conda create -n [your_new_environment_name]`

2. Activate the new conda environment

   - `conda activate [your_new_environment_name]`

3. Install PostgreSQL

   - `conda install postresql`

4. Install PostgREST

   - `conda install postgrest`

5. Create a local database

   - `initdb -D [your_new_db_name]`

6. Start the server modus / instance of postgres

   - `pg_ctl -D [your_new_db_name] -l logfile start`

7. **WAIT FOR SERVER TO START**
    
8. Create non-super user

   - `createuser --encrypted --pwprompt [your_non_super_user_name]`
   
9. Prompts for name / password

10. Create inner-database for non-super user
   
      - `createdb --owner=[your_non_super_user_name] [your_inner_db_name]`

11. At this point you can run a program and connect to `[your_inner_db_name]()`

---
### READ MORE BELOW ⬇️ Starting at #11
#### [Source](https://gist.github.com/gwangjinkim/f13bf596fefa7db7d31c22efd1627c7a)
##### ❗ Content reformatted for legibility ❗
---

This gist I write, because I couldn't find step by step instructions 
how to install and start postgresql locally (using conda within a conda environment - with the result
that you can run it without sudo/admin rights on your machine!)
and not globally in the operating system (which requires sudo/admin rights on that machine).

I hope, this will help especially people new to postgresql (and those who don't have sudo/admin rights on a specific machine but want
to run postgresql there)!


### 1. create conda environment
   - `conda create --name myenv`

### 2. enter the environment
   - `conda activate myenv`

### 3. install postgresql via conda
   - `conda install -y -c conda-forge postgresql`

### 4. create a base database locally
   - `initdb -D mylocal_db`

### 5. now start the server modus/instance of postgres
   - `pg_ctl -D mylocal_db -l logfile start`

### 6. waiting for server to start.... done
### 7. server started
### 8. now the server is up

### 9. create a non-superuser (more safety!)
   - `createuser --encrypted --pwprompt mynonsuperuser`
### 10. asks for name and password

### 11. using this super user, create inner database inside the base database
   - `createdb --owner=mynonsuperuser myinner_db`

### 11. in this point, if you run some program, you connect your program with this inner database
- > e.g. Django 

### 12. in django (Python) e.g. you open with your favorite editor:
   - `nano <mysite>/settings.py`
- or instead of [nano]() use your *favorite editor*!

>     DATABASES = {
>        'default': {
>        'ENGINE': 'django.db.backends.postgresql', /n
>        'NA ME': 'myinner_db', /
>        'USER': 'mynonsuperuser', /
>        'PASSWORD': '<mynonsuperuserpassword>', /
>        'HOST': 'localhost', /
>        'PORT': '', /
>        }
>     }

### 13. and it is available for django so that you can do with the connected program these further steps


### 14. first install psycopg2 because django requires this for handling postgresql
   - `conda install -c anaconda psycopg2`

### 15. then now you can do:
   - `python manage.py migrate`

### 16. to fully integrate the postgresql into your django website and to be able to use the database, you also need to create a superuser
   - `python manage.py createsuperuser --username name`

## Stop running the postgres instance under ubuntu

### 17. monitor whether a postgres instance/server is running or not
   - `ps aux | grep postgres`

### 18. if no instance is running, you will see only one line as the answer to your query - which is from your grep search! ending with: 
   - `grep --color=auto postgres`
   - >ignore this line

### 19. if an instance of postgresql server is running, then several processes are runnng. You can kill the server by the first number of the leading line!
   - `kill <number>`

the output of `ps aux | grep postgres` was:

> username  2673  0.0  0.0  14760   512 pts/11   S+   07:34   0:00 grep --color=auto postgres

> username 30550  0.0  0.0 179144 18996 ?        S    Jun13   0:01/home/username/miniconda3/envs/django/bin/postgres -D mylocal_db

> username 30552  0.0  0.0 179276  4756 ?        Ss   Jun13   0:00 postgres: checkpointer process

> username 30553  0.0  0.0 179144  5216 ?        Ss   Jun13   0:01 postgres: writer process   

> username 30554  0.0  0.0 179144  8464 ?        Ss   Jun13   0:01 postgres: wal writer process   

> username 30555  0.0  0.0 179700  5792 ?        Ss   Jun13   0:01 postgres: autovacuum launcher process   

> username 30556  0.0  0.0  34228  3416 ?        Ss   Jun13   0:03 postgres: stats collector process  

then  ***2673*** is just the `grep --color=auto postgres` so ignore

the line ending with `postgres -D /path/to/mylocal_db` is the leading line!

### 20. take first number occuring in this line (PID - process ID number) which is 30550, therefore kill it by:
   - `kill 30550`

## Run postgres as a non-server in the background

### 21. type the following 
   - `postgres -D db_djangogirls & # runs postgres`

   > press RET (return) to send it to background!

### 22. you can stop and switch to server mode by stop running postgres instance under ubuntu

stop non-server or server modus/instance of postgres
   - `ps aux | grep postgres`

### 23. see detailed instructions for finding the correct <process ID> under stop running postgres instance under ubuntu'! And then do:
   - `kill <process ID#>` to stop postgres


### 24. Have fun with your completely locally running - more safe - postgresql❗❗❗❗❗❗
