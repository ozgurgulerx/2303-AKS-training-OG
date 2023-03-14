# AKS - Azure DevOps Integration 

In this section we will extend the **Azure Voting App** deployment example in [AKS MS Learn page](https://learn.microsoft.com/en-us/azure/aks/learn/quick-kubernetes-deploy-cli).  
We will then integrate AKS deployment with Azure Devops Pipelines so that any change in the code or image Dockerfile will trigger the build and deploy stages to the cluster again. 

---
1. Fork the Voting App repo. (We will later create a Azure DevOps resource connection to our code repository in GitHub. This will work with any other code repository too.)
