# Rundeck test server

Deploy a Rundeck server on AWS using Ansible and run integration tests for [rundeck-backup-restore](https://github.com/jonatanblue/rundeck-backup-restore).

Ensure that your AWS access keys are in `~/.aws/credentials`:

```
[default]
aws_access_key_id=redacted
aws_secret_access_key=redacted
```

Set up a VPC, subnet, security group and EC2 SSH key.

Then run the playbook:

```
ansible-playbook -i "localhost," deploy.yml -e aws_region=${AWS_REGION?} -e ec2_key_name=${KEY_NAME?} -e ec2_security_group_id=${SECURITY_GROUP_ID?} -e ec2_subnet_id=${SUBNET_ID?}
```
