---
layout: post
title:  "centos 자주 쓰는 명령어"
date:   2015-03-14 13:31:01 +0800
categories: centos
tag: 
centos
명령어
---

* content
{:toc}

tail
==================
실시간 쌓이는 로그를 확인할 때
```
tail -f /data/mysql/mysqld.log
```

find
==================
내용에 포함되어 있는 파일명 찾기
```
find . -name "*.pin" | xargs grep -n "postback"
```

curl (text)
==================
```
curl -d "test=1" -X POST http://www.naver.com
```

curl-json-1
==================
response가 text/plain일때 사용
```
curl -i -v -X POST --cookie "cookiename1=cookievalue1; cookiename2=cookievalue2"  -H "Content-Type:application/json"  http://localhost:8080/api/url -d  '{"name01":"value01","name02":"value02"}'
```

curl-json-2
==================
response가 json일때 사용
```
curl -i -v -X POST --cookie "cookiename1=cookievalue1; cookiename2=cookievalue2"  -H "Content-Type:application/json" -H "Accept: application/json"  http://localhost:8080/api/url -d  '{"name01":"value01","name02":"value02"}'
```
