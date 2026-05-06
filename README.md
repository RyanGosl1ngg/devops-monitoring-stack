# DevOps Monitoring Stack

## Description
This project deploys a web service (nginx) with monitoring using Prometheus and Grafana.

## Architecture
nginx → nginx-exporter → Prometheus → Grafana 
node-exporter → Prometheus → Grafana

## Stack
- Docker / Docker Compose
- Nginx
- Prometheus
- Node Exporter
- Nginx Prometheus Exporter
- Grafana
- Ansible

## Security
Internal services are bound to 127.0.0.1
Access is provided via SSH tunneling

##  Access (SSH Tunnel)

Internal services (Grafana and Prometheus) are not exposed to the internet.
Access is provided via SSH tunneling.

### Grafana
ssh -L 3000:localhost:3000 root@servIP
http://localhost:3000

### Prometheus
ssh -L 9090:localhost:9090 root@servIP
http://localhost:9090

## Deploy
cd ansible
ansible-playbook -i inventory.ini deploy.yml

## Teardown
ansible-playbook -i inventory.ini teardown.yml
