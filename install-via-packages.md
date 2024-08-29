# pgEdge Package Downloads
Our enterprise-class packages run on all modern and popular Linux systems including EL8+, Ubuntu 22.04+, and Debian 12.  And yes... we also run on Amazon Linux 2023 & SLES 15.5+

&nbsp;

|         | RPM's <img width=40 height=40 src=img/enterprise-linux.png> | DEB's <img width=50 height=35 src=img/debian-ubuntu.png>               |
|---------|-------------------------------------------------------------|------------------------------------------------------------------------|
|         | &nbsp;<br> `sudo dnf install pgedge-pgXX-zzz.rpm` <br>&nbsp;| &nbsp;<br> `sudo apt-get install -f ./pgedge-pg16-amd64.deb` <br>&nbsp;|
| 5-Sep-24| [pgedge-pg16-amd64.rpm](https://pgedge.com)                 | [pgedge-pg16-amd64.deb](https://pgedge.com)                            |



## Running Setup to Configure 
After downloading the appropriate package & running one of the above commands to lay down the binaries, run our `setup` to configure a database as follows:

- first become the `pgedge` user and change into the `opt/pgedge` directory
```
sudo su - pgedge
cd /opt/pgedge
```

- then setup a database owned by the Super User & Password you designate
```
./pgedge setup -U user1 -P passwd1 -d db_name
```


