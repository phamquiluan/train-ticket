# Infra cheatsheet

## Prepare EC2 Machine 

Follow this document: https://github.com/phamquiluan/dotfiles/blob/master/INSTALL.md

## AWSCLI command

### Start instance 
```bash 
aws ec2 start-instances --instance-ids <instance-id> --region ap-southeast-2
```

### Change instance type 
```bash
 aws ec2 modify-instance-attribute --instance-id <instance-id> --region ap-southeast-2 --instance-type "{\"Value\":\"c5.12xlarge\"}"
 ```
