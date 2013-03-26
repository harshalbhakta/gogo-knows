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
#### Change default kernel version for Ubuntu grub
````ruby

$ sudo update-grub
$ grep menuentry /boot/grub2/grub.cfg

# Check the position of the kernel you want in the list.
# Set that as default in /etc/default/grub (position starts from 0)

$ sudo update-grub

````
