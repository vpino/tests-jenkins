# Install and Setup Jenkins in Canaima or Debian Jessie


## Install  

### First Step:

Download key and add it:

```bash
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
``` 

### Second Step:

Then add the following entry in your /etc/apt/sources.list: 

```bash
deb http://pkg.jenkins.io/debian-stable binary/
```

### Third Step

Update the system and install jenkins:

```bash
$ sudo apt update && apt install jenkins
``` 

### Four Step

Check the installation:

If you installed Jenkins locally, you find it running under the following URL: 

```bash
http://localhost:8080/
```


### Setup:


#### First install plugin:

In this case we go worked with a project in github (this).
So we need installed the plugins of git and github 

To this:

1 - Click in: ```Administrar Jenkins```.
2 - Click in: ```Administrar Plugins```.
3 - Check the plugin of ```git``` and ```github```.
4 - Click in: ```Downloand now```

#### Second step :: Create a Job


To this:

* 1 - Click in: ```New Job```.
* 2 - Type a Name.
* 3 - We created a project of freestyle.
* 4 - Fill out the general information.
* 5 - Section set source: Check ```Git``` and copy the url of project and brand to build.
* 6 - Section Trigger: Check ```Build when a change is pushed to GitHub```.
* 7 - Section Trigger: Check ```run periodically``` Because we want it to builded every 30 minutes also when a change is pushed to GitHub. So in the field copy the next: ```H/30 * * * *```.

* 8 - My project will do a directory synchronization for that in this step in the section Execute: Click in ```Execute Command shell``` and in the field copy the next: ```rsync -ravucz --exclude '*.git' --delete-delay rsy_ori/ rsy_des/```.

And finnish of configuration this simple job and now to check is worked 

Push a commit to repository or waiting for 30 minutes or Forced the build.



### Rsync Params:

* -r: Copiado recursivo.

* -a: Recursive copy and preserve modification times, but also copy symbolic links, preserve permissions, preserve owner information and file group.

* -v: Verbose progress command.

* -u: Update the content of the directory.

* -c: Checksum of the files, this ignore any files where checksum not match

* -z: Compress the information being transferred.

* --exclude-from: File with all files and directories ignored.

* --delete-delay: Delete the files and directories of more, after the synchronization is complete.




Sources:

[https://jenkins.io/]

[http://www.jveweb.net/archivo/2010/11/sincronizando-carpetas-con-rsync.html]


