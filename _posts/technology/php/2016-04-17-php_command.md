---
layout: post
title:  "php 자주 쓰는 명령어 및 함수"
date:   2016-04-17 13:31:01 +0800
categories: php
tag: php
---

* content
{:toc}

triple des 암호화
==================
```
// Encrypt
openssl_encrypt($text, "des-ede3-cbc", $key, OPENSSL_RAW_DATA, $iv);

// Decrypt
openssl_decrypt($ciphertext, "des-ede3-cbc", $key, OPENSSL_RAW_DATA, $iv);
```

AES256 + CBC + PKCS7
==================
```
$ky = "32자리";
$iv = "16자리";

$data = "김판근";

# AES256 encode
$enc_data = base64_encode(openssl_encrypt($data, "aes-256-cbc", $ky, true, $iv));

# AES256 decode
$dec_data = openssl_decrypt(base64_decode($enc_data), "aes-256-cbc", $ky, true, $iv);
```

모바일 접속 여부 판단
==================
```
function isMobile(){
$ua = $_SERVER['HTTP_USER_AGENT'];
$agent_code = 'w';
if(!preg_match('/(iPad)/i', $ua) && preg_match('/(iPhone|Mobile|UP.Browser|Android|BlackBerry|Windows CE|Nokia|webOS|Opera Mini|SonyEricsson|opera mobi|Windows Phone|IEMobile|POLARIS)/i', $ua)) {
  $agent_code = 'm';
}
return $agent_code;
}
```

파일 확장자 추출
==================
```
# 파일명에서 확장자를 추출하는 법
$filenm = "1.jpg";
$ext = strtolower(end(explode('.', $filenm)));
```

배열에 해당 키값이 포함되어 있는지 확인
==================
```
# key value 쌍으로 이루어진 배열
$code_array = array(
'910032'=>'435155',
'910012'=>'435156',
'910022'=>'435159'
);

# 해당 배열의 키값이 포함되는지를 체크
if(array_key_exists($변수,$code_array)) {
    //포함되어 있습니다.
}
```

특정 배열로 구성된 문자열이 포함되었는지 확인
==================
```
# 변수에 해당 문자열이 포함되어 있는지 확인
function strpos_array($haystack, $needles) {
    if ( is_array($needles) ) { #변수가 배열인지 확인
        foreach ($needles as $str) {
            if ( is_array($str) ) {
                $pos = strpos_array($haystack, $str);
            } else {
                $pos = strpos($haystack, $str); #문자열 처음 위치 반환
            }
            if ($pos !== FALSE) {
                return $pos;
            }
        }
    } else {
        return strpos($haystack, $needles);
    }
}

# 사용할때
$arr = array('FLOOR','INFORMATION_fSCHEMA','MIN(0)','0x71','CONCAT','OR 1','OR = 1','SLEEP');
if(strpos_array($query, $arr) > 0)
{
   echo "no hacking plz.. i am hungry..";
   die;
}
```

마이크로타임을 이용한 유일키값
==================
```
function Seqno() {
    $seqno = sha1(microtime(true));
    return $seqno;
}
```

간편하게 url 생성
==================
```
# URL 생성
function getURL($url, $data){
    if($data){
        if(strpos($url,"?") !== false) {
            $url = $url."&".$data;
        }else{
            $url = $url."?".$data;
        }
    }
    return $url;
}

$href = getURL("http://naver.com", "a=1&b=1");
$href = getURL("http://naver.com/?aa=1", "a=1&b=1");
```

현재시간 인덱스
==================
```
#현재날짜 반환
function nowDatetime(){
    return date('Y-m-d H:i:s');
}
#현재날짜 반환
function nowDateidx(){
    return strftime('%Y%m%d%H%M%S');
}
```

숫자 자리수 채우기
==================
```
$a = sprintf("%02d", $변수);
```