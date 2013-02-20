##![Linux](https://s3.amazonaws.com/gogo-knows/Linux.png)

### Tail command
```ruby

# Check the last lines of the file
$ tail production.log

# Live output
$ tail -f production.log
```

### Ubuntu system wide environment variable.
```ruby

# Put below line in the environment file.
$ vi /etc/environment

GREEN_QUIZYY_HOST="green.quizyy.com"

Note: Safest way to activate this change is to log out and login.

```
### Mac OS X Rails ENV variable.
```ruby

# Put below line in the .bash_profile file.
$ vi ~/.bash_profile

export GREEN_QUIZYY_HOST="green.quizyy.com"

# Reload bash_profile
. ~/.bash_profile

```
