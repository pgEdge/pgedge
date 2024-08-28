# pgEdge Package Downloads
Our enterprise-class packages run on all modern and popular Linux systems including EL8+, Ubuntu 22.04+, and Debian 12.  And yes... we also run on Amazon Linux 2023 & SLES 15.5+

&nbsp;
# RPM's

Download the RPM you'd like and then run the following command
```
sudo rpm -ivh pgedge-pg16-amd64.rpm
```

| Package Name                               | Date Released |
|--------------------------------------------|---------------|
| [pgedge-pg16-amd64.rpm](https://pgedge.com)| 5-Sep-24      |

&nbsp;
# DEB's
Download the DEB you'd like and then run the following command
```
sudo dpkg pgedge-pg16-amd64.deb
```

| Package Name                               | Date Released |
|--------------------------------------------|---------------|
| [pgedge-pg16-amd64.deb](https://pgedge.com)| 5-Sep-24      |

&nbsp;
# Running Setup to Configure 
Both Package formats install pgedge in `/opt/pgedge` as the `pgedge` user.   After running the above command to lay down the binaries...  run our setup as follows:

```
cd /opt/pgedge
./pgedge setup -U user1 -P passwd1 -d db_name
```


