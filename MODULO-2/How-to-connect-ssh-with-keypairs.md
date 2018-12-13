>-Use the chmod command (in bold below) to make sure your private key file isn’t publicly viewable. Please see commonly asked questions section below if you have issues and are using windows.

`chmod 400 /path_to_key/my_key.pem`

>- Finally, SSH to your EC2 instance (in bold below)

 `ssh -i /path_to_key/my_key.pem user_name@public_dns_name`

Ex:  

 `ssh -i ./DESENVOLVIMENTO.pem ec2-user@ec2-18-207-242-194.compute-1.amazonaws.com


https://medium.com/@GalarnykMichael/aws-ec2-part-2-ssh-into-ec2-instance-c7879d47b6b2`
