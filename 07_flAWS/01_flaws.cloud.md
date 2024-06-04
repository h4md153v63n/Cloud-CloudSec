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

![Uploading image.png…]()







