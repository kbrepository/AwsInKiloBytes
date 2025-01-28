# Overview
<p> This template will create a SNS Topic in you AWS account.</p>



## AWS CLI Command to validate template
```bash
aws cloudformation validate-template --template-body file:///<TemplatePath>> --region <REGION_NAME>
```

## AWS CLI Command to create resource
```bash
aws cloudformation create-stack --stack-name <STACKNAME> --template-body file://<TemplatePath> --region <REGION_NAME>
```

## AWS CLI Command to delete stack
```bash
aws cloudformation delete-stack --stack-name testSNSTopic --region us-east-1
```

### NOTE: 
This template is very basic, will be updating it and make it dynamic.
</html>