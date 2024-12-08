# avSudo
You have an unrooted device and want to use sudo in termux? This is the right .deb for you (you can use it even if u do have ur device rooted but mostly useless as its like just normal sudo but w/ some changes so unrooted phones can use it)


# Installing
### Firstly, lets remove the old sudo (even if u dont have it yet.)
```apt remove --purge sudo```

### Now, lets sync.
```dpkg --configure -a```

### (IF you dont have git installed)
### Install git
```apt install git```

### Now, clone the repo.
```git clone https://github.com/realcgcristi/avSudo.git```

### Lets cd to it.
```cd avSudo```

### Now, time to "install"
```dpkg -i sudo-noroot-new.deb```

### KEEP IN MIND: IT WILL FAIL.

### Now, that it gave a postinst file error, lets "fix it"
```rm -f /data/data/com.termux/files/usr/var/lib/dpkg/info/sudo.postinst```
```rm -f /data/data/com.termux/files/usr/var/lib/dpkg/info/sudo.*```

### Now, lets reconfigure it.
```dpkg --configure sudo```

### Now, edit the sudoers file.
```nano /data/data/com.termux/files/usr/etc/sudoers``` (and add ur user and put a password, i say u put all for perms - ```layout: username|All|password```)

### Enjoy!
