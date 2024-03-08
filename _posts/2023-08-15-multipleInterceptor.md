---
layout: contents
author: YellTa
title: "[스프링 인터셉터 중첩 로딩] [Spring Interceptor - multiple loading]"
permalink: :title
categories: ["spring"]
---
# Issue!
![multiple](..\assets\images\postImg\230815mutiple\mutiple.png)
프로젝트를 진행하던 중 Interceptor가 중첩되어 발생하는 문제를 발견했다.

I found the Spring Interceptor worked multiple.

## Find the Cause
![multiple2](..\assets\images\postImg\230815mutiple\multiple2.png)

Request URL 로그를 찍어서 요청을 확인해본 결과
처음 메인 페이지를 요청할 때 한 번이 아닌 여러번 요청하는 것을 알 수 있었다.

I added Request URL log and checked the result.
I found that multiple requests occurred when I entered my project's main page.

## Solve it

###  Requirement
URL에 해당하는 요청은 한 번만 이루어져야 한다.

Request corresponding to the URL is only executed one.

### Solution!
![configFile](..\assets\images\postImg\230815mutiple\modified.png)
내 Config 파일에서 exclude 옵션에 중첩으로 실행되는 URL을 추가했다.

I added URLs that loaded multiple to exclude option in my config file.



![IssueReport](..\assets\images\postImg\230815mutiple\issue.jpg)
###### <That's my IssueReport>
