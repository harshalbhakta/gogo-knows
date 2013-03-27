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

$ grep menuentry /boot/grub/grub.cfg

$ sudo vim /etc/default/grub

# Set the required entry fetched from grub.cfg as default in /etc/default/grub
GRUB_DEFAULT="Ubuntu, with Linux 3.5.0-25-generic"

$ sudo update-grub

# Changes are reflected in the file /boot/grub/grub.cfg

````
