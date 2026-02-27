# LGTM Stack Deployment

This Ansible playbook deploys the LGTM monitoring stack (Loki, Grafana, Prometheus, Alloy) using Docker Compose on a small cluster of one core node and two agent nodes with a web application installed.

**Core node stack**:
1. Nginx (reverse proxy)
2. Grafana
3. Prometheus
4. Loki (single scalable deployment)
5. Alloy - to scrape core node metrics
6. Blackbox Exporter

**Agent node stack**:
1. LEMP app (using php7.4) - https://github.com/hxamz/lemp-stack-ansible
2. Alloy

Alloy on agent node scraping php7.4-fpm logs (for basic example) and node metrics

Alloy on core node scraping node and cadvisor metrics

## Tests

Playbook tested on Ubuntu 24.04