# Challenge 6

**Challenge 6:** https://bigiamchallenge.com/challenge/6

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/9cb6d78a-ac4c-4c77-a7d1-281dabb34981)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/c5d73db0-7371-4017-8557-eaff2467d679)

View page source:

![Uploading image.png…]()



```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Principal": {
                "Federated": "cognito-identity.amazonaws.com"
            },
            "Action": "sts:AssumeRoleWithWebIdentity",
            "Condition": {
                "StringEquals": {
                    "cognito-identity.amazonaws.com:aud": "us-east-1:b73cb2d2-0d00-4e77-8e80-f99d9c13da3b"
                }
            }
        }
    ]
}
```

```
{
    &quot;Version&quot;: &quot;2012-10-17&quot;,
    &quot;Statement&quot;: [
        {
            &quot;Effect&quot;: &quot;Allow&quot;,
            &quot;Principal&quot;: {
                &quot;Federated&quot;: &quot;cognito-identity.amazonaws.com&quot;
            },
            &quot;Action&quot;: &quot;sts:AssumeRoleWithWebIdentity&quot;,
            &quot;Condition&quot;: {
                &quot;StringEquals&quot;: {
                    &quot;cognito-identity.amazonaws.com:aud&quot;: &quot;us-east-1:b73cb2d2-0d00-4e77-8e80-f99d9c13da3b&quot;
                }
            }
        }
    ]
}
```

```

```






