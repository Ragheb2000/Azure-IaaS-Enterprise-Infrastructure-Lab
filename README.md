# Azure IaaS Enterprise Infrastructure Lab

## Overview
This project documents a full **Azure IaaS enterprise-style infrastructure**  focusing on security, high availability, and production best practices.

The lab simulates a **medium-sized company environment** with no public IPs on virtual machines, centralized security, and highly available application and database tiers.

---

## Objectives
- Design a secure Azure network architecture
- Implement High Availability for application and database layers
- Enforce outbound traffic inspection using Azure Firewall
- Remove direct RDP access and manage VMs securely via Azure Bastion
- Prepare the environment for Hybrid connectivity

---

## Architecture Summary
- **VNET:** 10.0.0.0/16
- Segmented subnets (Frontend, Backend, Firewall, Gateway, Bastion)
- Internal Load Balancers only
- Azure Firewall with Forced Tunneling
- Azure Bastion for secure administration
- SQL Server Always On Availability Groups

---

## Key Technologies
- Azure Virtual Network
- Azure Firewall
- Azure Load Balancer (Internal)
- Azure Bastion
- Windows Server
- SQL Server Always On (IaaS)
- Availability Sets
- VPN Gateway (Hybrid-ready)

---

## Security Design Highlights
- No Public IPs on Virtual Machines
- All outbound traffic routed through Azure Firewall
- NAT rules for RDP fully removed
- Bastion used as the only administrative access method
- Network segmentation and least privilege access

---

## High Availability
- Application tier protected by Availability Set + Load Balancer
- Database tier protected by:
  - Windows Failover Cluster
  - SQL Server Always On Availability Groups
  - Internal Load Balancer with Floating IP

---

## Validation
- Load balancing verified from external client (Jumpbox)
- Health probes confirmed healthy
- SQL failover tested without application disruption
- Bastion access validated without opening inbound ports

---

## Outcome
This lab demonstrates a **production-ready Azure IaaS design** aligned with Microsoft best practices and real-world enterprise requirements.

It can be used as:
- A personal portfolio project
- Interview discussion reference
- Foundation for advanced Azure or Hybrid architectures
