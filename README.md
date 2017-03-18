# Devops Java demo
This will Deploy Java App on Tomcat Server with Nginx as a Reverse Proxy Server.
Prometheus and Grafana will be deployed for Monitoring.

# Perrequisites
* Centos 7
* Ansible 2.2.1.0

# Update Configurations
* Update the Inventory Files
* Update vars for Each in there respective directory like :- ``` roles/tomcat/vars/main.yml ```

# Code Deploy and Monitoring Stack
```
ansible-playbook main.yml -i inventory
```

# To view Running Application
* update your hosts file with following enteries
```
<ip address of centos 7 machine > tomcat.demo.com promethous.demo.com grafana.demo.com
```

# For Backup of Mysql Database

```
ansible-playbook Backup.yml -i inventory
```
