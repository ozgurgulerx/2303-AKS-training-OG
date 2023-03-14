# AKS - Azure DevOps Integration 

In this section we will extend the **Azure Voting App** deployment example in [AKS MS Learn page](https://learn.microsoft.com/en-us/azure/aks/learn/quick-kubernetes-deploy-cli).  
We will then integrate AKS deployment with Azure Devops Pipelines so that any change in the code or image Dockerfile will trigger the build and deploy stages to the cluster again. 

---
1. Fork the Voting App repo. (This is required because we will later create a Azure DevOps **resource connection** to our code repository in GitHub. Will work with any other code repository too.)

`git clone https://github.com/ozgurgulerx/azure-voting-app-redis-test01`

2. Create your AKS Cluster 

`az group create --name rg-aks-01 --location uksouth`
`az aks create - rg-aks-01  -n aks-cluster-01 \ `
`--enable-managed-identity --node-count 1 \ `
`--enable-addons monitoring --enable-msi-auth-for-monitoring `
` --generate-ssh-keys`