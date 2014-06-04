# BOSH Deployment for kafka

To use this bosh deployment manifest :

```
bosh target BOSH_HOST
bosh login
git clone ssh://git@stash.hybris.com:7999/idefix/bosh-release-kafka.git
cd bosh-release-kafka
bosh deployment deployments/aws/ec2/us-east/kafka-aws-ec2-us-east-1-manifest.yml
bosh deploy
```

** if you want to deploy to bosh-lite, you can use the manifest _kafka-warden-manifest.yml_.
