# Hello, Here we are practicing our `Kubernetes concepts` on AWS Elastic Kubernetes Service!

## Create `EKS Cluster` Using the following commands below:- 

```
# Imperative Way
eksctl create cluster --name demo --version 1.28 --nodegroup-name demo-ng --node-type t2.micro --nodes 3 --managed
```
```
# Declarative Way
eksctl create cluster -f EKS_Custom.yaml
```
## Create EKS Cluster and `NodeGroup separately` using the following commands below:- 

```
eksctl create cluster --name=eksdemo1 \
--region=us-east-1 --zones=us-east-1a,us-east-1b \
--without-nodegroup
``` 

```
eksctl create nodegroup --cluster=eksdemo1 --region=us-east-1 \ --name=eksdemo1-ng-public1 \
--node-type=t2.micro --nodes=2 --nodes-min=2 --nodes-max=4 \ --node-volume-size=20 --ssh-access --ssh-public-key=kube-demo \ --managed --asg-access --external-dns-access --full-ecr-access \
--appmesh-access --alb-ingress-access
```

## OIDC Credentials Provider:-

```
eksctl utils associate-iam-oidc-provider --region us-east-1 \
--cluster eksdemo1 --approve
```