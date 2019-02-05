---
layout: post
title:  "git realtime deploy"
date:   2014-11-17 13:31:01 +0800
categories: git
tag: git
---

* content
{:toc}

#1 bare 저장소 생성
```
mkdir 프로젝트명.git
git init --bare --shared
```

#2 git 저장소 생성
```
프로젝트 폴더에서 git init
```

#3 git 저장소에 기존 프로젝트 파일 밀어넣기
```
git add .
git commit -m "first download all file"
```

#4 git 저장소와 bare저장소를 연결
```
다른서버 : git remote add origin ssh://iptour@211.117.60.113/home/iptour/iptour.git
같은서버 : git remote add origin /home/iptour/iptour.git
git push origin master
```

#5 source tree에서 clone으로 bare저장소를 연결

#6 자동 배포
1) bare 저장소를 활용할때
```
hooks post-update 이름 변경
권한 변경 : chmod -x post-update
hooks > post-update에 쉘 추가
. /var/www/html/pull.sh # git 서버와 배포 서버가 같을 경우 사용
ssh <user_id>@<server_ip> "/var/www/html/pull.sh" # git 서버와 배포 서버가 다를 경우 사용
```

2)  non-bare 저장소를 사용할떄
```
hooks post-update 이름 변경
권한 변경 : chmod -x post-update
hooks > post-update에 체크아웃 구문 추가
GIT_WORK_TREE=/home/iptour git checkout -f
```

#7 부록
```
======pull.sh======
#!/bin/sh
unset GIT_DIR
cd /var/www/html/
echo "start git pull"
exec git pull origin master
echo "finish"
======pull.sh======
```