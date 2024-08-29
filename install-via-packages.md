# pgEdge Package Downloads
Our enterprise-class packages run on all major Linux distro's including EL8+, Ubuntu 22.04+, and Debian 11+.  

And yes... we also run on Amazon Linux 2023 & SLES 15

|         | RPM's <img width=40 height=40 src=img/enterprise-linux.png> | DEB's <img width=50 height=35 src=img/debian-ubuntu.png>               |
|---------|-------------------------------------------------------------|------------------------------------------------------------------------|
|         | &nbsp;<br> `sudo dnf install pgedge-pgXX-zzz.rpm` <br>&nbsp;| &nbsp;<br> `sudo apt-get install -f ./pgedge-pg16-amd64.deb` <br>&nbsp;|
| 5-Sep-24| [pgedge-pg16-amd64.rpm](https://pgedge.com)                 | [pgedge-pg16-amd64.deb](https://pgedge.com)                            |



## Running Setup to Configure 
After downloading the appropriate package & running one of the above commands to lay down the binaries, run our `setup` to configure a database as follows:

First become the `pgedge` user and change into the `opt/pgedge` directory
```
sudo su - pgedge
cd /opt/pgedge
```

Then setup your database owned by the Postgres superuser & password you designate
```
./pgedge setup -U user1 -P passwd1 -d db_name
```


