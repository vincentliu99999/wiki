# CodeDeploy

## Log

- agent log: `/var/log/aws/codedeploy-agent/codedeploy-agent.log`
- agent install, update log: `/tmp/codedeploy-agent.update.log`
- deployment log: `/opt/codedeploy-agent/deployment-root/deployment-logs/codedeploy-agent-deployments.log`
- Appspec script log: `/opt/codedeploy-agent/deployment-root/deployment-group-ID/deployment-ID/logs/scripts.log`

## copy deployment

前一次 depolyment script 失敗時使用

```shell
cd /opt/codedeploy-agent/deployment-root/
rm -rf *

less /opt/codedeploy-agent/deployment-root/deployment-logs/codedeploy-agent-deployments.log
```