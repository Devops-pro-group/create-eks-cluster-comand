# create-eks-cluster-comand
#Create Eks cluster via command line 
# How to create EKS cluster via command line 
# I - Follow these steps =====>
# 1 Install ekscl 
    choco install -y eksctl
# 2 To create a cluster run this :This command will create a Kubernetes cluster in the us-east-1 region with four t2.micro worker nodes. It might take several minutes to complete. 

      eksctl create cluster --name ikeitalab-cluster --region us-east-1--nodes 4 --node-type t2.micro
# 3  Wait for 5 to 6 minutes for your cluster to be ready and run the following commands 
    aws eks update-kubeconfig --region us-east-1 --name  ikeitalab-cluste
    kubectl get nodes 
# 4 Delete the cluster using command line
    # Delete first your nodegroup 
    aws eks delete-nodegroup --nodegroup-name your-nodegroup-name --cluster-name your-cluster-name
    aws eks delete-cluster --name yourclastername
