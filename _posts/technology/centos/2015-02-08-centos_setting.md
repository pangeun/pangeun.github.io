---
layout: post
title:  "centos 네트워크 설정"
date:   2014-11-17 13:31:01 +0800
categories: centos
tag: centos
---

* content
{:toc}

hostname 변경 파일
==================
- /etc/sysconfig/network

네임서버 설정 파일
==================
- /etc/resolv.conf
- nameserver를 구글로 변경한다.

랜카드 설정 파일
==================
- /etc/sysconfig/network-scripts/ifcfg-eth0

루프백 설정 파일
==================
- /etc/sysconfig/network-scripts/ifcfg-lo
