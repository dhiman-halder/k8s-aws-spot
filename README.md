# k8s-aws-spot

Extremely low cost 2 node Kubernetes cluster setup with Kubeadm running ubuntu 16.04+ based EC2 spot instances. Master node is t3a.small and Worker node is t3a.micro. Per hour running cost for the 2 instances is typically less than 1 cent an hour!

## Instructions

1. Deploy the CloudFormation Template. As a pre-requisite you need to have an EC2 Key pair. Choose that as a parameter during the run.

2. SSH into the master EC2 node. There should be a file called join.txt. Cat it and copy its contents to clipboard

3. SSH into the node01 EC2 node. Paste the contents of the join.txt file (from clipboard) and run the command

4. Do a Kubectl get nodes from the master node - you should see the 2 node cluster ready now!

The Kubernetes cluster is installed using kubeadm and networking plugin installed is calico.
