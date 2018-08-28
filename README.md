# CloudFront redirect for Intercom
AWS [CloudFormation](https://aws.amazon.com/cloudformation/) stack for setting up a [CloudFront](https://aws.amazon.com/cloudfront/) Distribution redirect to custom origin with SSL configured to support TLSv1.1 and above.

Based on the the information from the [Intercom Developer site](https://developers.intercom.com/installing-intercom/docs/set-up-your-custom-domain?showHidden=f2cb6)

## Parameters
- `DomainName` Required
- `PreExistingLogsBucket` optional
- `CertificateArn` Required

## Usage

### Create the stack

```shell
aws cloudformation deploy --template-file templates/master.yml --stack-name docs-intercom --parameter-overrides $(cat parameters/example.com)
```

### Delete the stack

```shell
aws cloudformation delete-stack --stack-name docs-intercom
```
**Note:** the S3 logging bucket will need to be manually deleted

## Route 53 (DNS)
This stack does not create the Route 53 DNS entry that is left to the user.
