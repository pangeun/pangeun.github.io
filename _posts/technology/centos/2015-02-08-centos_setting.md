---
layout: post
title:  "centos 네트워크 설정"
date:   2014-11-17 13:31:01 +0800
categories: git
tag: git
---

* content
{:toc}

/etc/sysconfig/network
==================
- hostname을 변경해야 한다.

/etc/resolv.conf
==================
- nameserver를 구글로 변경한다.

랜카드 설정 파일
==================
/etc/sysconfig/network-scripts/ifcfg-eth0

루프백 설정 파일
==================
/etc/sysconfig/network-scripts/ifcfg-lo
