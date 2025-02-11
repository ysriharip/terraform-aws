# terraform-eks
A sample repository to create EKS on AWS using Terraform.

### Install AWS CLI 

As the first step, you need to install AWS CLI as we will use the AWS CLI (`aws configure`) command to connect Terraform with AWS in the next steps.

Follow the below link to Install AWS CLI.
```
https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html
```

### Install Terraform

Next, Install Terraform using the below link.
```
https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli
```

### Connect Terraform with AWS

Its very easy to connect Terraform with AWS. Run `aws configure` command and provide the AWS Security credentials as shown in the video.

### Initialize Terraform

Clone the repository and Run `terraform init`. This will intialize the terraform environment for you and download the modules, providers and other configuration required.

### Optionally review the terraform configuration

Run `terraform plan` to see the configuration it creates when executed.

### Finally, Apply terraform configuation to create EKS cluster with VPC 

`terraform apply`


## We App Deployment
->Build a docker file for inginx web app

docker build -t hari-demo:nginx-prom-new .

docker tag hari-demo:nginx-prom-new 141136133910.dkr.ecr.us-west-1.amazonaws.com/hari-deme:nginx-prom-new

docker push 141136133910.dkr.ecr.us-west-1.amazonaws.com/hari-demo:latest

aws ecr get-login-password --region us-west-1 | docker login --username AWS --password-stdin 141136133910.dkr.ecr.us-west-1.amazonaws.com


## Deploy kubernetes Deployment manifest files and resources using kubectl CLI
kubectl apply -f nginx-deployment.yaml

kubectl apply -f nginx-exporter.yaml

kubectl apply -f prometheus-config.yaml

kubectl apply -f prometheus-deployment.yaml

kubectl apply -f nginx-loadbalancer.yaml


![image](https://github.com/user-attachments/assets/40aa87aa-04b4-4ab5-8ca7-26a280df6ea2)



## Prometheus Monitoring :

![Screenshot 2025-02-11 145726](https://github.com/user-attachments/assets/110e1266-3f28-4af1-a860-928c9ff30993)
