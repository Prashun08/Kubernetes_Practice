<h3>Hello, Here we are practicing our <span style="background-color: #FFFF00">Kubernetes</span> concepts on AWS Elastic Kubernetes Service!</h3>
<h5>Create <mark>EKS Cluster</mark> Using the following commands below:- </h5>
<ol><li><h6>Imperative Way</h6>eksctl create cluster --name demo --version 1.28 --nodegroup-name demo-ng --node-type t2.micro --nodes 3 --managed</li>
<li><h6>Declarative Way</h6>eksctl create cluster -f EKS_Custom.yaml</li>
</ol>