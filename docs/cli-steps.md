# CLI Deployment Steps

This document provides Azure CLI commands for deploying the SRE-Load-Balancer solution.

## Steps

1. Create resource group
2. Create VNet and subnet
3. Create NSG and rules
4. Deploy VMSS with NGINX/IIS
5. Create and configure Load Balancer
6. Set up health probes
7. Validate deployment

See scripts/az-deploy-vmss-nginx.sh for automation.
