# Hadoop 2.6.0 multi node installation using anisble
-----
This playbook deploys Apache hadoop 2.6.0 multi node on Ubuntu 14.04 LTS using vagrant.


### To run this playbook:
To Install multi node hadoop head over to the directory in which the Playbook is located and use the command below
```
vagrant up
```

**Note:** Change below details in vars/main file of the roles 
```
 hostname_master: hadoopmaster
 hostname_slave: hadoopslave
 hadoop_user: root
 hadoop_group: root
 hadoopmaster_ip: 192.168.1.78
 hadoopslave_ip: 192.168.1.79
 
```
 
For Namenode web UI open http://localhost:50070

For ResourceManager open http://localhost:8088

##### To start hadoop : 
 Open terminal on hadoopmaster node and execute the command to start hadoop 
```
'/usr/local/hadoop-2.6.0/sbin/start-all.sh' 
```

