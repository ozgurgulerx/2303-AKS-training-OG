# AKS - Azure DevOps Integration 

In this section we will extend the **Azure Voting App** deployment example in [AKS MS Learn page](https://learn.microsoft.com/en-us/azure/aks/learn/quick-kubernetes-deploy-cli).  
We will then integrate AKS deployment with Azure Devops Pipelines so that any change in the code or image Dockerfile will trigger the build and deploy stages to the cluster again. 

---
1. Fork the Voting App repo. (This is required because we will later create a Azure DevOps **resource connection** to our code repository in GitHub. Will work with any other code repository too.)

`git clone https://github.com/ozgurgulerx/azure-voting-app-redis-test01`

2. Create your AKS Cluster 

Create a new resource-group which is a container to envelope a subgroup of your Azure resources.  
rg-name must be unique.  

`az group create --name rg-aks-01-ozg --location uksouth`  

Create a new AKS cluster...
`az aks create -g rg-aks-01-ozg  -n aks-cluster-0314 \ `  
`--enable-managed-identity --node-count 1 \ `  
`--enable-addons monitoring --enable-msi-auth-for-monitoring \`  
` --generate-ssh-keys`  

Enable kubectl...
`az aks get-credentials --resource-group rg-aks-01-ozg  --name aks-cluster-0314`  


3. Deploy the app onto your AKS cluster.  
`kubectl create -f azure-vote-all-in-one-redis.yaml`  

4. Confirm the deployment and get the service IP to test the deployment.  

![Image](../../../../Downloads/2023-03-14%2010.21.57%20AM.png)

<img src="../../../../Downloads/2023-03-14%2010.21.57%20AM.png" />
