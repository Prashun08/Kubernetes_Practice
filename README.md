<h3>Hello, Here we are practicing our Kubernetes concepts on AWS Elastic Kubernetes Service!</h3>
<h5>Create EKS Cluster Using the following commands below:- </h5>
<ol><li><h6>Imperative Way</h6>eksctl create cluster --name demo --version 1.28 --nodegroup-name demo-ng --node-type t2.micro --nodes 3 --managed</li>
<li><h6>Declarative Way</h6>eksctl create cluster -f EKS_Custom.yaml</li>
</ol>
<h5>Create EKS Cluster and NodeGroup separately using the following commands below:- </h5>

<ul>
<li>eksctl create cluster --name=eksdemo1 \<br>
--region=us-east-1 \<br>
--zones=us-east-1a,us-east-1b \<br>
--without-nodegroup </li>

<li>eksctl create nodegroup --cluster=eksdemo1 \<br>
--region=us-east-1 \<br>
--name=eksdemo1-ng-public1 \<br>
--node-type=t2.micro \<br>
--nodes=2 \<br>
--nodes-min=2 \<br>
--nodes-max=4 \<br>
--node-volume-size=20 \<br>
--ssh-access \<br>
--ssh-public-key=kube-demo \<br>
--managed \<br>
--asg-access \<br>
--external-dns-access \<br>
--full-ecr-access \<br>
--appmesh-access \<br>
--alb-ingress-access</li>
</ul>

<h5>OIDC Credentials Provider:-</h5>

<ul><li>eksctl utils associate-iam-oidc-provider \<br>
--region us-east-1 \<br>
--cluster eksdemo1 \<br>
--approve</li>
</ul>