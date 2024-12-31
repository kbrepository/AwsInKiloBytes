# Overview
<p> This template will create a security group in you AWS account.</p>

## Steps 


__Depends On__

- VPC
## Reference


Here are the steps to execute the above YAML template to create an AWS Security Group:

---

### **1. Prerequisites**
- **AWS CLI** installed and configured with appropriate permissions.
- **Access to CloudFormation** with a role that can create security groups.
- A **VPC ID** where the security group will be created.

---

### **2. Save the Template**
1. Save the provided YAML content to a file named `security-group-template.yaml` on your local machine.

---

### **3. Prepare Parameters**
Identify or decide on the following inputs:
- `VpcId`: The ID of the VPC where the Security Group will be created.
- `SecurityGroupName` (Optional): Name for the Security Group.
- `SecurityGroupDescription` (Optional): A description for the Security Group.
- `IngressRules` and `EgressRules` (Optional): Lists of rules in the following format:
  ```yaml
  - IpProtocol: tcp
    FromPort: 22
    ToPort: 22
    CidrIp: 0.0.0.0/0
  ```

---

### **4. Execute the Template**
#### Option 1: **AWS Management Console**
1. Go to the [AWS CloudFormation Console](https://console.aws.amazon.com/cloudformation/).
2. Click **Create Stack** → **With new resources (standard)**.
3. Upload the `security-group-template.yaml` file.
4. Provide the required parameter values.
5. Click **Next** and follow the prompts to create the stack.

#### Option 2: **AWS CLI**
1. Use the `aws cloudformation deploy` command to create the stack.

   Example:
   ```bash
   aws cloudformation deploy \\
       --template-file security-group-template.yaml \\
       --stack-name MySecurityGroupStack \\
       --parameter-overrides \\
       VpcId=vpc-0123456789abcdef0 \\
       SecurityGroupName=MySecurityGroup \\
       SecurityGroupDescription="Custom security group created dynamically." \\
       IngressRules='[{"IpProtocol":"tcp","FromPort":22,"ToPort":22,"CidrIp":"0.0.0.0/0"}]' \\
       EgressRules='[{"IpProtocol":"tcp","FromPort":80,"ToPort":80,"CidrIp":"0.0.0.0/0"}]'
   ```

2. Verify the output for the **SecurityGroupId** once the stack is created successfully.

---

### **5. Verify the Security Group**
After creation, verify the Security Group in the **EC2 Management Console**:
1. Navigate to **EC2** → **Security Groups**.
2. Search for the name or ID of the newly created security group.
3. Review the ingress and egress rules to confirm they match the configuration.

---

### **6. Clean Up**
If you no longer need the Security Group, delete the CloudFormation stack:
```bash
aws cloudformation delete-stack --stack-name MySecurityGroupStack
```

This will clean up all resources created by the stack.