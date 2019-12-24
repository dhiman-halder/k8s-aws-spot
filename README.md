# k8s-aws-spot

Extremely low cost 2 node Kubernetes cluster setup with Kubeadm running ubuntu 16.04+ based EC2 spot instances. Master node is t3a.small and Worker node is t3a.micro. Per hour running cost for the 2 instances is typically less than 1 cent an hour!

## Instructions

1. Deploy the CloudFormation Template. As a pre-requisite you need to have an EC2 Key pair. Choose that as a parameter during the run.

2. SSH into the master EC2 node. There should be a file called join.txt. Cat it and copy its contents to clipboard

3. SSH into the node01 EC2 node. Paste the contents of the join.txt file (from clipboard) and hit enter

4. Do a Kubectl get nodes from the master node terminal - you should see the 2 node cluster ready now!

5. To delete the cluster, delete the CloudFormation stack.

Note that the Kubernetes cluster is installed using the kubeadm tool. The container runtime installed is docker and the networking plugin is calico.

Enjoy & use at your own risk! if you have questions, email me at dhiman.halder@gmail.com

This project is licensed under the terms of the MIT license.
