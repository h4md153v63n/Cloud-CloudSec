# flaws.cloud
+ http://flaws.cloud/

<center>
<pre>
 .d888 888        d8888 888       888  .d8888b.
d88P"  888       d88888 888   o   888 d88P  Y88b
888    888      d88P888 888  d8b  888 Y88b.
888888 888     d88P 888 888 d888b 888  "Y888b.
888    888    d88P  888 888d88888b888     "Y88b.
888    888   d88P   888 88888P Y88888       "888
888    888  d8888888888 8888P   Y8888 Y88b  d88P
888    888 d88P     888 888P     Y888  "Y8888P"
</pre>
</center>


## Solutions
- [Level 1](https://github.com/h4md153v63n/CloudSec/blob/main/07_flAWS/01_flaws.cloud.md#level-1)
- [Level 2](https://github.com/h4md153v63n/CloudSec/blob/main/07_flAWS/01_flaws.cloud.md#level-2)
- [Level 3](https://github.com/h4md153v63n/CloudSec/blob/main/07_flAWS/01_flaws.cloud.md#level-3)
- [Level 4](https://github.com/h4md153v63n/CloudSec/blob/main/07_flAWS/01_flaws.cloud.md#level-4)
- [Level 5](https://github.com/h4md153v63n/CloudSec/blob/main/07_flAWS/01_flaws.cloud.md#level-5)
- [Level 6](https://github.com/h4md153v63n/CloudSec/blob/main/07_flAWS/01_flaws.cloud.md#level-6)


### Level 1:
```
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $dig flaws.cloud

; <<>> DiG 9.16.42-Debian <<>> flaws.cloud
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 55957
;; flags: qr rd ra; QUERY: 1, ANSWER: 8, AUTHORITY: 0, ADDITIONAL: 0
;; WARNING: Message has 8 extra bytes at end

;; QUESTION SECTION:
;flaws.cloud.			IN	A

;; ANSWER SECTION:
flaws.cloud.		5	IN	A	52.92.204.19
flaws.cloud.		5	IN	A	52.92.186.27
flaws.cloud.		5	IN	A	52.92.227.187
flaws.cloud.		5	IN	A	52.92.192.203
flaws.cloud.		5	IN	A	52.92.233.211
flaws.cloud.		5	IN	A	52.218.132.66
flaws.cloud.		5	IN	A	52.92.209.99
flaws.cloud.		5	IN	A	52.92.232.251

;; Query time: 160 msec
;; SERVER: 192.168.1.1#53(192.168.1.1)
;; WHEN: Tue Jun 04 13:19:21 IST 2024
;; MSG SIZE  rcvd: 165

┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $nslookup flaws.cloud
Server:		192.168.1.1
Address:	192.168.1.1#53

Non-authoritative answer:
Name:	flaws.cloud
Address: 52.218.168.146
Name:	flaws.cloud
Address: 52.218.236.122
Name:	flaws.cloud
Address: 52.92.163.83
Name:	flaws.cloud
Address: 52.92.185.59
Name:	flaws.cloud
Address: 52.92.185.251
Name:	flaws.cloud
Address: 52.92.203.3
Name:	flaws.cloud
Address: 52.92.207.99
Name:	flaws.cloud
Address: 52.218.153.90
** server can't find flaws.cloud: NOTIMP
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/ea24c754-1743-4832-9c9f-8de4cc23c69c)


```
┌─[✗]─[cwl@RedCloud]─[~/Desktop]
└──╼ $nslookup 52.218.168.146
146.168.218.52.in-addr.arpa	name = s3-website-us-west-2.amazonaws.com.

Authoritative answers can be found from:
218.52.in-addr.arpa	nameserver = pdns1.ultradns.net.
218.52.in-addr.arpa	nameserver = x2.amazonaws.com.
218.52.in-addr.arpa	nameserver = x4.amazonaws.org.
218.52.in-addr.arpa	nameserver = x1.amazonaws.com.
218.52.in-addr.arpa	nameserver = x3.amazonaws.org.
x1.amazonaws.com	internet address = 156.154.64.10
x2.amazonaws.com	internet address = 156.154.65.10
x3.amazonaws.org	internet address = 156.154.150.1
x4.amazonaws.org	internet address = 204.74.120.1
pdns1.ultradns.net	internet address = 204.74.108.1
pdns1.ultradns.net	has AAAA address 2001:502:f3ff::1
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/75269f94-1c21-4954-88cb-885ac590174e)

Visit: http://s3-us-west-2.amazonaws.com/flaws.cloud

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/fe0fe170-3a3c-402e-b2e8-f630d5b624e9)

Navigate: http://s3-us-west-2.amazonaws.com/flaws.cloud/secret-dd02c7c.html

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/f5dfa251-2694-44ec-92ea-da3c1d9927ee)


### Level 2:







