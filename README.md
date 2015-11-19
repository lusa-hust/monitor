# influxdb-cadvisor-grafana

Incoporating influxdb, cadvisor and grafana for monitoring docker containers

# How to config and run

Setup user and password for influxdb at ./development/group_vars/all  
E.g.
  ```yaml
  influx_user: root
  influx_passwd: root
  ```
Setup user and password for grafana at ./development/group_vars/all  
E.g.
  ```yaml
  grafana_user: admin
  grafana_passwd: admin
  ```
Modify grafana ip in `<hostfile>`  
example hostfile:
```
[webservers]
10.141.141.10 ansible_ssh_private_key_file=<"path to ssh private key"> server_ip=10.141.141.10
10.141.141.11 ansible_ssh_private_key_file=<"path to ssh private key"> server_ip=10.141.141.11

[localhost]
127.0.0.1 grafana_server=10.141.141.10 server_ip=10.141.141.10,10.141.141.11
```

Deploy
  ```bash
  $ ansible-playbook -i <hostfile> site.yml
  ```
