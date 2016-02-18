# Hadoop 2.6.0 multi node installation using anisble
-----
This playbook deploys Apache hadoop 2.6.0 multi node on Ubuntu 14.04 LTS.

## To use this Playbook:

Edit the ansible `hosts inventory` file :
```
[hadoopmaster]
192.168.1.78

[hadoopslaves]
192.168.1.79
```
 Replace the `ip adress` of hadoopmaster and hadoopslave.


### To run this playbook:

```
ansible-playbook site.yml --extra-vars "hostname_master=hadoopmaster hostname_slave=hadoopslave remote_user=harpreet hadoop_user=hsbaath hadoop_group=root"
```

**Note:** Change below details in above ansible command. 
```
hostname_master # hadoop master hostname
hostname_slave  # hadoop slave hostname
remote_user  # remote user used by ansible 
hadoop_user # hadoop user 
hadoop_group # hadoop group 
```
 
For Namenode web UI open http://localhost:50070

For ResourceManager open http://localhost:8088

##### To start hadoop : 
 Open terminal on hadoop master and execute the command to start hadoop 
```
'/usr/local/hadoop-2.6.0/sbin/start-all.sh' 
```

