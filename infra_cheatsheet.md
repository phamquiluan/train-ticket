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

### Get instance type
```bash
aws ec2 describe-instances --instance-ids i-001e25e5b4f9f7e51 --region ap-southeast-2 | jq .Reservations[0].Instances[0].InstanceType
```

### Change instance type 
```bash
aws ec2 modify-instance-attribute --instance-id <instance-id> --region ap-southeast-2 --instance-type "{\"Value\":\"c5.12xlarge\"}"
```
 
 | Instance Type | vCPUs    | RAM    |
|---------------|----------|--------|
| t2.medium     | 2 vCPUs  | 4 GiB  |
| t2.large      | 2 vCPUs  | 8 GiB  |
| t2.xlarge     | 4 vCPUs  | 16GiB  |
| c5.4xlarge    | 16 vCPUs | 32GiB  |
| c5.12xlarge   | 48 vCPUs | 96 GiB |

### Get instance status
```bash 
aws ec2 describe-instances --instance-ids <instance-id> --region ap-southeast-2 | jq .Reservations[0].Instances[0].State.Name
```
