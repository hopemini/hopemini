---
title:  "디렉토리 내의 모든 파일들 이름 일괄 변경/파일내용 일괄 변경"
excerpt: "디렉토리 내의 모든 파일들 이름 일괄 변경/파일내용 일괄 변경 방법 "

categories:
  - Blog
tags:
  - [Blog, Linux]

toc: true
toc_sticky: true
 
date: 2022-05-04
last_modified_at: 2022-05-05
---

# 디렉토리 내의 모든 파일들 이름 일괄 변경/파일내용 일괄 변경

## 하위 디렉토리 파일 내용 치환
```
$ find ./ -type f | xargs sed -i 's/from/to/g'
```
현재 디렉토리 내의 모든 파일들의 내용중 from 을 to로 바꾼다.

## 하위 디렉토리 파일 이름 변경
```
$ find ./ -name "*from*"  | sed -e 'p' -e "s/from/to/g" |xargs -n 2 mv
```
현재 디렉토리 내의 모든 파일, 디렉토리의 이름중 from이 포함된 파일, 디렉토리의 이름의 from을 to로 바꾼다.


