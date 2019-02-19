# System Manager

IAM Role

- AWS managed policy - `AmazonEC2RoleforSSM`

Log

- `/var/log/amazon/ssm/amazon-ssm-agent.log`
- `/var/log/amazon/ssm/hibernate.log`

## 安裝步驟

2017.09 之後的 AMI 已預設安裝，下列僅適用 `Intel (x86_64)`，給 EC2 的 user data

```shell
#!/bin/bash

# install SSM Agent
yum install -y https://s3.amazonaws.com/ec2-downloads-windows/SSMAgent/latest/linux_amd64/amazon-ssm-agent.rpm

# start SSM Agent
start amazon-ssm-agent

# check status
status amazon-ssm-agent

# using proxy https://docs.aws.amazon.com/zh_tw/systems-manager/latest/userguide/sysman-proxy-with-ssm-agent.html
echo -e "env http_proxy=http://proxy.com:3128\nenv https_proxy=http://proxy.com:3128\nenv no_proxy=169.254.169.254" |  tee /etc/init/amazon-ssm-agent.override

stop amazon-ssm-agent
start amazon-ssm-agent
```