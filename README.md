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
Modify grafana ip in <hostfile>  

Deploy
  ```bash
  $ ansible-playbook -i <hostfile> site.yml
  ```
