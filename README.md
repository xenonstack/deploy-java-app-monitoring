# Java Application Deployment, Monitoring & Backup by Ansible
This will Deploy Java App on Tomcat Server with Nginx as a Reverse Proxy Server.
Prometheus and Grafana will be deployed for Monitoring.

# Perequisites
* Centos 7
* Ansible 2.2.1.0
* Selinux Disabled

# Bootstrap
* Add ssh key of root user to given instance.

### Update Configurations files
* Update the Inventory Files
* Update vars for Each in there respective directory like :- ``` roles/tomcat/vars/main.yml ```

### Deploy Application and Monitoring Stack
```
ansible-playbook main.yml -i inventory
```

### To view Running Application
Update your hosts file with following entries.

```
* <ip address of centos 7 machine>
* tomcat.demo.com
* promethous.demo.com
* grafana.demo.com
```

 Note: You need to add data source in grafana dashboard manually to view graphs for mysql and application monitoring. Name should be "Prometheus" of datasource.


### Add Graphs in Grafana
Add following mentioned json file for Graphs to Grafana Dashboard. add all the json file from graph folder to grafana server

### For Backup of Mysql Database

```
ansible-playbook backup.yml -i inventory
```
