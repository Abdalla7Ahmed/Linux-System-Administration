

## 1.files Compression 
### gzip --> fast 
### bzip2 --> high compression rate
![gzip](images/1.1-gzip.png)

![bzip2](images/1.2-bzip2.png)

![unzip](images/1.3-unzip.png)


### compression directories and files 
### we will use tar to archive tree of files and directories
```bash
$ tar cf <tar-name.tar> <files to archive>
cf --> create file
```
![archive](images/1.4-tar.png)


```bash
$ tar xf <tar-name.tar> 
xf --> extract, file
```

![archive](images/1.5-tar.png)


### how to compress files and directories ?

### 1. gzip compression
```bash
$ tar cfz <tar-name.tar.gz> <files to copress>
$ tar xfz <tar-name.tar.gz> 

```
![compress](images/1.6-tar.gz.png)

### .bz2 compression
```bash
$ tar cfj <tar-name.tar.bz2> <files to copress>
$ tar xfj <tar-name.tar.bz2> 
```

![compress](images/1.7-tar.bz2.png)
