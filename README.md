# AWS

> Creates a VPC and two ec2 instances 1 in Public and other in Private
> Public instance : Bastion Host
> Private instance: Apache Web server


## Install

### Windows
Install AWS CLI using the installer https://s3.amazonaws.com/aws-cli/AWSCLI64.msi

### Linux/Mac

```
$ pip install awscli --upgrade --user
```


## Usage

Create a new AWS S3 bucket (Ex: S3Bucket)
Copy all the files into the S3 bucket
Create a KeyPair in EC2 (Ex: test-keypair)

```
$ aws cloudformation create-stack --stack-name <stack-name>  --template-body file://customer_init_master.yml --capabilities CAPABILITY_NAMED_IAM --parameters ParameterKey=EnvironmentName,ParameterValue=dev ParameterKey=AvailabilityZone1,ParameterValue=us-west-2a  ParameterKey=KeyName,ParameterValue=<test-keypair> ParameterKey=InstanceWebAmi,ParameterValue=ami-a9d09ed1 ParameterKey=TemplateBucket,ParameterValue=<S3Bucket>
```
