# CNF-kubernetes-project
Cloud-native network functions deployed on Kubernetes, including firewall, IDS, load balancing, scaling, and rolling updates.



# Containerized Network Functions (CNF) on Kubernetes

## Project Overview
Deployed a production-grade service chain of containerized network 
functions on Google Kubernetes Engine (GKE) demonstrating how CNFs 
outperform traditional VM-based network appliances in agility, 
scalability, and resilience.

## Architecture
Traffic Flow:
Internet → Load Balancer (NGINX) → Firewall (Squid) → IDS (Netshoot)

## CNFs Deployed
- **Firewall** (Squid) — 2 replicas for high availability
- **Load Balancer** (NGINX) — 2 replicas, public-facing
- **IDS Monitor** (Netshoot) — Network traffic inspection

## What This Demonstrates

### Resilience
- Pod auto-recovery in under 30 seconds vs minutes for VM recovery
- Kubernetes automatically replaces failed containers

### Scalability  
- Scaled firewall from 2 to 5 replicas in under 10 seconds
- Zero manual intervention required

### Agility
- Rolling updates with zero downtime
- Single command deployment vs hours of VM provisioning

## Tech Stack
- Google Kubernetes Engine (GKE)
- Docker
- kubectl
- NGINX, Squid, Netshoot

## Commands Used
kubectl apply -f firewall.yaml
kubectl apply -f loadbalancer.yaml
kubectl apply -f ids.yaml
kubectl apply -f service-chain.yaml
