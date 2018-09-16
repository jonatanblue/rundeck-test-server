# Rundeck test server

Integration tests for [rundeck-backup-restore](https://github.com/jonatanblue/rundeck-backup-restore) using Ansible and AWS.

[![CircleCI](https://circleci.com/gh/jonatanblue/rundeck-test-server/tree/master.svg?style=svg)](https://circleci.com/gh/jonatanblue/rundeck-test-server/tree/master)

Ensure that your AWS keys are in `~/.aws/credentials`:

```
[default]
aws_access_key_id=redacted
aws_secret_access_key=redacted
```

You need to set up a VPC, subnet and EC2 SSH key. The rest is handled by Ansible.

To run the playbook:

```
ansible-playbook -i "localhost," deploy.yml -e aws_region=${AWS_REGION?} -e ec2_key_name=${KEY_NAME?} -e ec2_security_group_id=${SECURITY_GROUP_ID?} -e ec2_subnet_id=${SUBNET_ID?} ec2_vpc_id=${VPC_ID?}
```
