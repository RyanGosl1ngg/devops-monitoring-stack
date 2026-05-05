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

## Deploy
cd ansible
ansible-playbook -i inventory.ini deploy.yml

## Teardown
ansible-playbook -i inventory.ini teardown.yml
