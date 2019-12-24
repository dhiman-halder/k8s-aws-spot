# k8s-aws-spot

Kubernetes cluster with Kubeadm with 2 ubuntu 16.04+ based EC2 nodes running spot instances

Instructions

1. Deploy the CloudFormation Template. As a pre-requisite you need to have an EC2 Key pair. Choose that as a parameter during the run.

2. SSH into the master EC2 node. There should be a file called join.txt. Cat it and copy its contents to clipboard

3. SSH into the node01 EC2 node. Paste the contents of the join.txt file (from clipboard) and run the command

4. Do a Kubectl get nodes from the master node - you should see the 2 node cluster ready now!

The Kubernetes cluster is installed using kubeadm and Calico is used as the networking plugin.
