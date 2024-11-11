### Category: SEC – Threat Detection and Incident Response
Demostrate how user lost ssh keys / stolen how to change it and recommend ssm instead.
```bash
An organization allows most of its employees to work from home using their company-issued laptops. There was a recent incident in which a developer’s laptop, which doesn’t have any encryption at all, was stolen. The device contains several SSH private keys that are used to access Amazon Linux EC2 instances in the corporate AWS account. The Security Administrator has separate SSH private keys to access all instances.

What should the Administrator do to protect currently running EC2 instances?

Log in to the Amazon EC2 console and delete the key pairs.

Use the modify-instance-attribute command in the AWS CLI to change the associated SSH key of the affected EC2 instances.

Use the AWS Systems Manager Run Command to modify the ~/.ssh/authorized_keys file of all affected EC2 instances. Remove all public keys in the file that is associated with the compromised SSH private keys.
Use AWS Config to easily disable the compromised SSH keys and block access to the affected EC2 instances.
Correct
When you launch an instance, you are prompted for the name of a key pair. If you plan to connect to the instance using SSH, you must specify a key pair. At boot time, the public key content is placed on your Linux instance in an entry within ~/.ssh/authorized_keys. When you connect to your Linux instance using SSH, you must specify the private key that corresponds to the public key content to log in.

Because Amazon EC2 doesn’t keep a copy of your private key, there is no way to recover a private key if you lose it. However, there can still be a way to connect to instances that use a lost key pair.

You can use the AWS Systems Manager Run command to remotely and securely manage the configuration of your managed nodes. A managed node can be an EC2 instance, edge device, or on-premises server or virtual machine (VM) in your hybrid environment that has been configured for Systems Manager.



Run Command allows you to automate common administrative tasks and perform one-time configuration changes at scale. You can use Run Command from the AWS Management Console, the AWS Command Line Interface (AWS CLI), AWS Tools for Windows PowerShell, or the AWS SDKs.

Hence, the correct answer is: Use the AWS Systems Manager Run Command to modify the ~/.ssh/authorized_keys file of all affected EC2 instances. Remove all public keys in the file that is associated with the compromised SSH private keys.

The option that says: Log in to the Amazon EC2 console and delete the key pairs is incorrect because deleting a key pair doesn’t affect the private key on your computer or the public key on any instances that already launched using that key pair. You have to modify the ~/.ssh/authorized_keys file of all affected EC2 instances.

The option that says: Use the modify-instance-attribute command in the AWS CLI to change the associated SSH key of the affected EC2 instances is incorrect because the attributes that can be modified by the modify-instance-attribute command doesn’t include SSH keys.

The option that says: Use AWS Config to easily disable the compromised SSH keys and block access to the affected EC2 instances is incorrect because AWS Config is not capable of disabling SSH keys used in Amazon EC2 instances. AWS Config is primarily used to assess, audit, and evaluate the configurations of your AWS resources.

 

References:

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/replacing-lost-key-pair.html

 

Tutorials Dojo’s AWS Certified Security – Specialty Exam Study Guide:

https://tutorialsdojo.com/aws-certified-security-specialty-exam-study-path/

```
Migrate encrypted to unencrypted
```bash
https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html#migrate-data-encrypted-unencrypted
```
