# ALB-CloudFormation
creates load balancer in aws with AutoScaling group and launch template.

## Instances:  
min instances = 1  
max instances = 4  
desired = 2
no public ip  
run web server  

## VPC:
Public Subnets = 2  
Private Subnets = 2  
Nat Gateway
Internet Gateway

## Use:
aws cloudformation create-stack --stack-name ALBTest --template-body file://alb.yaml --parameters ParameterKey=EnvironmentName,ParameterValue=YourParamValue  
*set YourParamValue 

Alternate CIDRs:  
aws cloudformation create-stack --stack-name ALBTest --template-body file://alb.yaml --parameters ParameterKey=EnvironmentName,ParameterValue=TestAlb ParameterKey=VPCCIDR,ParameterValue=XXX.XXX.0.0/16 ParameterKey=PublicSubnet1CIDR,ParameterValue=XXX.XXX.XXX.0/24  ParameterKey=PublicSubnet2CIDR,ParameterValue=XXX.XXX.XXX.0/24  ParameterKey=PrivateSubnet1CIDR,ParameterValue=XXX.XXX.XXX.0/24  ParameterKey=PrivateSubnet2CIDR,ParameterValue=XXX.XXX.XXX.0/24  
*set XXX.XXX.XXX
