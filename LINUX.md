##![Linux](https://s3.amazonaws.com/gogo-knows/Linux.png)

### Remove all .svn folders in a project folder
```ruby

# Execute this from the project folder
$ rm -rf `find . -type d -name .svn`

```

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
[https://help.ubuntu.com/community/Grub2/Submenus](https://help.ubuntu.com/community/Grub2/Submenus)
````ruby

$ sudo update-grub

$ grep menuentry /boot/grub/grub.cfg

$ sudo vim /etc/default/grub

# Set the required entry fetched from grub.cfg as default in /etc/default/grub
# use > for sub-menu entry
GRUB_DEFAULT="Advanced options for Ubuntu>Ubuntu, with Linux 3.5.0-25-generic"

$ sudo update-grub

# Changes are reflected in the file /boot/grub/grub.cfg

````

#### Show grub menu by default
[https://help.ubuntu.com/community/Grub2#Hidden](https://help.ubuntu.com/community/Grub2#Hidden)
````ruby

Comment out below lines from /etc/default/grub

#GRUB_HIDDEN_TIMEOUT=0
#GRUB_HIDDEN_TIMEOUT_QUIET=true

````

#### Check currently running kernel version
````ruby

$ uname -a

or

$ uname -r

````

#### Unicorn zombiee process
````ruby

# List PID's
$ lsof /tmp/my_app.socket

# Kill
$ kill -9 pid

# If above steps don't work, try this.
$ ps aux | grep unicorn

````
