



in systemd services use system control (systemctl) to execute any command 
and journald that use journal control (journalctl) for logs


-  active (running) --> active in the current shell
- enabled -->enable when restart 
- vendor preset: enabled) the default is enable when install 




### systemv runlevels 
- run level 0 --> poweroff
 - run level 1 --> single user
 - run level 2 --> multi user without GUI and NFS 
 - run level 3 --> multi user without GUI (CMI) -->default runlevel for servers 
 - run level 4 -->unused (for feature )
 - run level 5 --> multi user + GUI -->default runlevel for desktop
 - run level 6 --> restart 


```bash
$runlevel
N 5    ---> N not determinde, 5 current runlevel
```


### How it work ?
every runlevel has scripts start with S or K (s for start , k for kill) and number (the order)
when the runlevel start it run all the scripts in order 
example : 
if the current runlevel is 0 --> it will execute all the K{number}{scrpit name} in order 
if the current runlevel is 5 --> it will execute all the S{umber}{script name} in order
### systemd targets
multiuser.target(as run level 2 ,3)
graphical.target (as run level 5)
rescue.target(as run level 1 --> single )
poweroff.target
reboot.target



```bash
$systemctl get-default
graphical.target
$runlevel
N 5

$systemctl set-default multi-user.target
$runlevel 
5 3   --> it was 5 and now 3 
```


if we reboot the machine no GUI provide



how can i switch between targets without reboot ?
by using isolate
```bash
$systemctl isolate graphicaltarget   #will open the GUI
$systemctl set-default graphical.target
```


### How it work ?
when we start the service the systemctl create symbolic link in /et/systmd/system
when we stop the service the systemctl remove the symbolic link


note that 
the default symbolic link is link to the default target
```bash
root@abdallah:~# ls -l /etc/systemd/system/default.target 
lrwxrwxrwx 1 root root 36 سبت 25 19:36 /etc/systemd/system/default.target -> /lib/systemd/system/graphical.target

```



### mask & unmask 

mask used to mask the service mean if we try to start it , it will fail
unmask to make the service available to start




