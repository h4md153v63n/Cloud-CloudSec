# Challenge 3

**Challenge 3:** https://bigiamchallenge.com/challenge/3

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/f6eeae81-e16d-4eef-9b81-efe28552ffa7)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/54ec8c68-a9ca-4c0c-ade5-9f48fc427390)



```
{
    "Version": "2008-10-17",
    "Id": "Statement1",
    "Statement": [
        {
            "Sid": "Statement1",
            "Effect": "Allow",
            "Principal": {
                "AWS": "*"
            },
            "Action": "SNS:Subscribe",
            "Resource": "arn:aws:sns:us-east-1:092297851374:TBICWizPushNotifications",
            "Condition": {
                "StringLike": {
                    "sns:Endpoint": "*@tbic.wiz.io"
                }
            }
        }
    ]
}
```

```
xxx
```

