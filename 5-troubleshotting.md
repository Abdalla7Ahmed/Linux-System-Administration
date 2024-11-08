### 1-Disable ctrl+alt+delete


this hot key run the ctrl-alt-del.target which is symbolic link to the reboot.target
when this hot key pressed the system will reboot 

we can't edit this target because it symbolic link to reboot so any change will reflect to the reboot target .


the solution is find way to remove this symbolic link 
```bash
root@abdallah:/etc/systemd/system# ls -l ctrl-alt-del.target 
lrwxrwxrwx 1 root root 13 نوف 21  2023 ctrl-alt-del.target -> reboot.target
root@abdallah:/usr/lib/systemd/system# 
```


to remove this link , just mask it 

```bash
root@abdallah:/etc/systemd/system# systemctl mask ctrl-alt-del.target
Created symlink /etc/systemd/system/ctrl-alt-del.target → /dev/null.
root@abdallah:/usr/lib/systemd/system# 
```

and then make the system control read the configuration again 

```bash
root@abdallah:/etc/systemd/system# systemctl daemon-reload 
```



### note 
the systemctl search first for the links in the /etc/systemd/system if no service found it search in /user/lib/systemd/system


