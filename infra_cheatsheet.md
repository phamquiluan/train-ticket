# Infra cheatsheet

## Prepare EC2 Machine 

Follow this document: https://github.com/phamquiluan/dotfiles/blob/master/INSTALL.md

## AWSCLI command

### Get instance id 
```bash 
aws ec2 describe-instances --region ap-southeast-2 | jq .Reservations[0].Instances[0].InstanceId
```

### Start instance 
```bash 
aws ec2 start-instances --instance-ids <instance-id> --region ap-southeast-2
```

### Change instance type 
```bash
 aws ec2 modify-instance-attribute --instance-id <instance-id> --region ap-southeast-2 --instance-type "{\"Value\":\"c5.12xlarge\"}"
 ```

### Get instance status
```bash 
aws ec2 describe-instances --instance-ids <instance-id> --region ap-southeast-2 | jq .Reservations[0].Instances[0].State.Name
```

### Get instance type
```bash
aws ec2 describe-instances --instance-ids i-001e25e5b4f9f7e51 --region ap-southeast-2 | jq .Reservations[0].Instances[0].InstanceType
```
