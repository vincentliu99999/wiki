# CloudWatch

## CloudWatch Agent

### IAM Role

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "logs:CreateLogGroup",
        "logs:CreateLogStream",
        "logs:PutLogEvents",
        "logs:DescribeLogStreams"
    ],
      "Resource": [
        "arn:aws:logs:*:*:*"
    ]
  }
 ]
}
```

### 安裝 CloudWatch Logs agent

```shell
# 下載並單獨執行
cd ~
curl https://s3.amazonaws.com/aws-cloudwatch/downloads/latest/awslogs-agent-setup.py -O
curl https://s3.amazonaws.com/aws-cloudwatch/downloads/latest/AgentDependencies.tar.gz -O
tar xvf AgentDependencies.tar.gz -C /tmp/
sudo python ./awslogs-agent-setup.py --region ap-northeast-1 --dependency-path /tmp/AgentDependencies # enter 就好

# optional: proxy 設定
sudo vim /var/awslogs/etc/proxy.conf

/var/awslogs/bin/awslogs-version.sh | less # 版本查詢
sudo service awslogs start # 啟動 awslogs 服務
sudo chkconfig awslogs on # 每次系統啟動時啟動 awslogs 服務
ps -ef|grep awslog # 檢查process是否有啟動
less /var/log/awslogs.log
```

指令

```shell
# Linux 2: systemctl start awslogsd
service awslogs status # /etc/init.d/awslogs status
service awslogs stop # /etc/init.d/awslogs stop
service awslogs start # /etc/init.d/awslogs start
service awslogs restart # /etc/init.d/awslogs restart
```

### Log

設定 - script 安裝

- /var/awslogs/etc/awslogs.conf
- /var/awslogs/etc/awscli.conf 地區設定
- /var/awslogs/etc/
- /var/log/awslogs.log
- /var/log/awslogs-agent-setup.log

## Reference

- [Quick Start: Install and Configure the CloudWatch Logs Agent on a Running EC2 Linux Instance](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/QuickStartEC2Instance.html)
- [CloudWatch Logs Agent Reference](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/AgentReference.html) agent 設定檔說明

## Archive

yum 安裝

```shell
sudo yum update -y
sudo yum install -y awslogs
# 預設 region 為 us-east-1
sudo vim /etc/awslogs/awscli.conf # region 改為 ap-northeast-1
```

設定 - yum 安裝

- /etc/awslogs/awslogs.conf
- /etc/awslogs/awscli.conf 地區設定
- /etc/awslogs/
- /var/log/awslogs.log