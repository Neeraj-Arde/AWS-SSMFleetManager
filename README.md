# AWS-SSMFleetManager
Connect with fleet manager

```bash
Login to AWS account and serach for IAM.
Create a user with prefered name and attach policies as mentioned below.
1. AmazonEC2readonlyaccess
2. AmazonSSMfullAccess
3. Need to create a custom policy as below
```

# Custom Policy
```bash

{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "ssm-guiconnect:StartConnection",
                "ssm-guiconnect:*"
            ],
            "Resource": [
                "arn:aws:ec2:ap-south-1:767397743033:instance/*",
                "*"
            ]
        }
    ]
}

```
# Instance Connectivity

```bash
Instance should have appropriate SSM role.
Go to actions.
Click on monitoring and trouble shooting.
Select Fleet manager, it will redirect us to managed nodes.
In fleet manager Instance will be displayed as a node.
Go to node actions, Click on connect.
Select connect with remote desktop.
We can Login with 2 ways, one with username and password, other is with Keypair
Provide the correct credentials and RDP will get displayed on screen.
```

