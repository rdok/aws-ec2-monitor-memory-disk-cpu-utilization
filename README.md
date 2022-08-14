# Monitor memory and disk usage
Showcase monitoring memory and disk usage by install CloudWatch agent through CloudFormation on an EC2.

![metrics](./metrics.png "Stress Results")

## Stress Test
```sh
sudo amazon-linux-extras install -y epel
sudo yum install -y stress-ng htop

# Run all the stress tests in parallel, for one minute, with 1 instance of each being run: 
# t3.medium 2 cpu, 4 GB
sudo stress-ng --all 1 --timeout 2m

stress-ng --cpu 2 --timeout 5m --metrics-brief
```

## Development
- `make samconfig.toml` && customise as per you needs
- `make deploy`

## Sources

[Install CloudWatch Agent](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Install-CloudWatch-Agent.html)  
[Metrics collected by the CloudWatch agent on Linux instances](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/metrics-collected-by-CloudWatch-agent.html#linux-metrics-enabled-by-CloudWatch-agent)  
[Inline CloudFormation Template](https://github.com/awslabs/aws-cloudformation-templates/blob/master/aws/solutions/AmazonCloudWatchAgent/inline/amazon_linux.template)
