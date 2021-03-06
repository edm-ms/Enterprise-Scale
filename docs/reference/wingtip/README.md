| Enterprise-Scale Design Principles | ARM Template | Scale without refactoring |
|:-------------|:--------------|:--------------|
|![Best Practice Check](https://azurequickstartsservice.blob.core.windows.net/badges/subscription-deployments/create-rg-lock-role-assignment/BestPracticeResult.svg)|[![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://ms.portal.azure.com/?feature.customportal=false#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2FAzOps%2Fmain%2Ftemplate%2Fux-foundation.json)  | Yes |

# Deploy Enterprise-Scale foundation

## Customer profile

This reference implementation is ideal for customers who want to start with landing zones for their workload in Azure, where hybrid connectivity to their on-premise datacenter is not required from the start.

## How to evolve and add support for hybrid connectivity later

If the business requirements changes over time, such as migration of on-prem applications to Azure that requires hybrid connectivity, the architecture allows you to expand and implement networking without refactoring Azure Design with minimal disruption to what is already in Azure. Architecture allows to create the connectivity subscription and place it into the platform management group and assign Azure Policy for the target networking topology using either Virtual WAN or Hub and Spoke networking topology.

## Pre-requisites

To deploy this ARM template, your user/service principal must have Owner permission at the tenant root.
See the following [instructions](https://docs.microsoft.com/en-us/azure/role-based-access-control/elevate-access-global-admin) on how to grant access.

## What will be deployed?

- A scalable management group hierarchy aligned to core platform capabilities, allowing you to operationalize at scale using RBAC and Policy
- Azure Policies that will enable autonomy for the platform and the landing zones
- An Azure subscription dedicated for management, which enables core platform capabilities at scale such as security, auditing, and logging
- Landing Zone management group for Azure native, internet-facing applications and resources, which doesn't require hybrid connectivity. This is where you will create your subscriptions that will host your workloads

![Enterprise-Scale without connectivity](./media/es-without-networking.PNG)
