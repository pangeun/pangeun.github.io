---
layout: post
title:  "centos 자주 쓰는 명령어"
date:   2015-03-14 13:31:01 +0800
categories: centos
tag: centos
---

* content
{:toc}

1. 실시간 쌓이는 로그를 확인할 때
```
tail -f /data/mysql/mysqld.log
```

2. 내용에 포함되어 있는 파일명 찾기
```
find . -name "*.pin" | xargs grep -n "postback"
```

3. curl-text
```
curl -d "test=1" -X POST http://www.naver.com
```

4. curl-json > response-text
```
curl -i -v -X POST --cookie "cookiename1=cookievalue1; cookiename2=cookievalue2"  -H "Content-Type:application/json"  http://localhost:8080/api/url -d  '{"name01":"value01","name02":"value02"}'
```

5. curl-json > response-json
```
curl -i -v -X POST --cookie "cookiename1=cookievalue1; cookiename2=cookievalue2"  -H "Content-Type:application/json" -H "Accept: application/json"  http://localhost:8080/api/url -d  '{"name01":"value01","name02":"value02"}'
```
