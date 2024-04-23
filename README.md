<h3>Hello, Here we are practicing our Kubernetes concepts on AWS Elastic Kubernetes Service!</h3>
<h5>Create EKS Cluster Using the following commands below:- </h5>
<ol><li><h6>Imperative Way</h6>eksctl create cluster --name demo --version 1.28 --nodegroup-name demo-ng --node-type t2.micro --nodes 3 --managed</li>
<li><h6>Declarative Way</h6>eksctl create cluster -f EKS_Custom.yaml</li>
</ol>
<h5>Create EKS Cluster and NodeGroup separately using the following commands below:- </h5>
<ul>
<li>eksctl create cluster --name=eksdemo1 \
                      --region=us-east-1 \
                      --zones=us-east-1a,us-east-1b \
                      --without-nodegroup </li>
<li>eksctl create nodegroup --cluster=eksdemo1 \
                       --region=us-east-1 \
                       --name=eksdemo1-ng-public1 \
                       --node-type=t2.micro \
                       --nodes=2 \
                       --nodes-min=2 \
                       --nodes-max=4 \
                       --node-volume-size=20 \
                       --ssh-access \
                       --ssh-public-key=kube-demo \
                       --managed \
                       --asg-access \
                       --external-dns-access \
                       --full-ecr-access \
                       --appmesh-access \
                       --alb-ingress-access</li>
</ul>
<h5>OIDC Credentials Provider:-</h5>
<ul><li>eksctl utils associate-iam-oidc-provider \
    --region us-east-1 \
    --cluster eksdemo1 \
    --approve</li></ul>