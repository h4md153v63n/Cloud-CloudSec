# Challenge 4

**Challenge 4:** https://bigiamchallenge.com/challenge/4

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/cdbab321-9873-4577-9033-2a969f2c0eef)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/66e7fe21-902c-4a14-85df-8f3c74bc4a44)




```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::thebigiamchallenge-admin-storage-abf1321/*"
        },
        {
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:ListBucket",
            "Resource": "arn:aws:s3:::thebigiamchallenge-admin-storage-abf1321",
            "Condition": {
                "StringLike": {
                    "s3:prefix": "files/*"
                },
                "ForAllValues:StringLike": {
                    "aws:PrincipalArn": "arn:aws:iam::133713371337:user/admin"
                }
            }
        }
    ]
}
```

```
xxx
```



