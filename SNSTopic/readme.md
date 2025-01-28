# Overview
<p> This template will create a SNS Topic in you AWS account.</p>

## AWS CLI Command to validate template

aws cloudformation validate-template --template-body file:///<TemplatePath>> --region <REGION_NAME>

## AWS CLI command to create resource
aws cloudformation create-stack --stack-name <STACKNAME> --template-body file://<TemplatePath> --region <REGION_NAME>

### NOTE: 
This template is very basic, will be updating it and make it dynamic.
