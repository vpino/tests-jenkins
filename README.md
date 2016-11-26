# Install and Setup Jenkins in Canaima or Debian Jessie


## Install Jenkis 

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


### Setup Jenkins


