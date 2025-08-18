# PowerShell Deployment Steps

This document provides PowerShell commands for deploying the SRE-Load-Balancer solution.

## Steps

1. Create resource group
2. Create VNet and subnet
3. Create NSG and rules
4. Deploy VMSS with NGINX/IIS
5. Create and configure Load Balancer
6. Set up health probes
7. Validate deployment

See scripts/ps-deploy-vmss-nginx.ps1 for automation.
