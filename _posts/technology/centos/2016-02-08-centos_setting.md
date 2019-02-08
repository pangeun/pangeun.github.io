---
layout: post
title:  "centos 네트워크 설정"
date:   2016-02-08 13:31:01 +0800
categories: centos
tag: centos
---

* content
{:toc}

1. 호스트 설정
```
/etc/hosts
```

2. 호스트네임 설정
```
/etc/sysconfig/network
```

3. 네임서버 설정
- nameserver를 구글로 변경한다.
```
/etc/resolv.conf

```

4. 랜카드 설정
```
/etc/sysconfig/network-scripts/ifcfg-eth0
```

5. 루프백 설정
```
/etc/sysconfig/network-scripts/ifcfg-lo
```
