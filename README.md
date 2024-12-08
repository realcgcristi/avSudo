# avSudo
You have an unrooted device and want to use sudo in termux? This is the right .deb for you (you can use it even if u do have ur device rooted but mostly useless as its like just normal sudo but w/ some changes so unrooted phones can use it)


# Installing
### Firstly, lets remove the old sudo (even if u dont have it yet.)
```apt remove --purge sudo```

### Now, lets sync.
```dpkg --configure -a```

### Install git (IF you dont have git installed)
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

</br>
</br>

### QnA

Q: I get the error "*username* isn't in the sudoers file" </br>
</br>
A: Add your user, the sudoers file is located at /data/data/com.termux/files/usr/etc/sudoers - use nano, etc. to edit, layout is: *username*|All|*password*
</br>
</br>
Q: I get an error that idk how to fix </br> 
</br>
A: Github Issues, tell me there anything.
</br>
</br>
Q: Will this give me FULL access to everything possible? </br>
</br>
A: For the most part, yes. avSudo provides root-like access for most commands. However, some unrooted devices are still limited by the system kernel. While avSudo removes many restrictions, certain kernel-level limitations may still apply.

</br>
</br>

### What is avSudo? Why does it exist?

I originally created avSudo for myself because I needed root access for using Docker (yes, I got it working!). Since Docker requires root for some commands, I built avSudo to provide a way to use sudo on unrooted devices. Now, I'm releasing it so others can use it for tasks that would normally require root access, enabling more functionality on unrooted devices.
