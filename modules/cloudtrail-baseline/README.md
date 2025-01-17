# cloudtrail-baseline

Enable CloudTrail in all regions and deliver events to CloudWatch Logs. CloudTrail logs are encrypted using AWS Key Management Service.

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| aws\_account\_id | The AWS Account ID number of the account. | string | n/a | yes |
| cloudtrail\_name | The name of the trail. | string | `"cloudtrail-multi-region"` | no |
| cloudwatch\_logs\_group\_name | The name of CloudWatch Logs group to which CloudTrail events are delivered. | string | `"cloudtrail-multi-region"` | no |
| cloudwatch\_logs\_retention\_in\_days | Number of days to retain logs for. CIS recommends 365 days.  Possible values are: 0, 1, 3, 5, 7, 14, 30, 60, 90, 120, 150, 180, 365, 400, 545, 731, 1827, and 3653. Set to 0 to keep logs indefinitely. | string | `"365"` | no |
| iam\_role\_name | The name of the IAM Role to be used by CloudTrail to delivery logs to CloudWatch Logs group. | string | `"CloudTrail-CloudWatch-Delivery-Role"` | no |
| iam\_role\_policy\_name | The name of the IAM Role Policy to be used by CloudTrail to delivery logs to CloudWatch Logs group. | string | `"CloudTrail-CloudWatch-Delivery-Policy"` | no |
| key\_deletion\_window\_in\_days | Duration in days after which the key is deleted after destruction of the resource, must be between 7 and 30 days. Defaults to 30 days. | string | `"10"` | no |
| region | The AWS region in which CloudTrail is set up. | string | n/a | yes |
| s3\_bucket\_name | The name of the S3 bucket which will store configuration snapshots. | string | n/a | yes |
| s3\_key\_prefix | The prefix for the specified S3 bucket. | string | `""` | no |

## Outputs

| Name | Description |
|------|-------------|
| cloudtrail | The trail for recording events in all regions. |
| kms\_key | The  KMS key used for encrypting CloudTrail events. |
| log\_delivery\_iam\_role | The IAM role used for delivering CloudTrail events to CloudWatch Logs. |
| log\_group | The CloudWatch Logs log group which stores CloudTrail events. |

<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
