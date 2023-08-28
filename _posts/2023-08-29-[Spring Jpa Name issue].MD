---
layout: post
author: YellTa
title: "[스프링 JPA 이름 오류!] [Spring JPA name Issue]"
tags: [java, backend]
categories: ["Memo","Spring","Web"]
---


#  my Setting  - 내가 한 세팅
![Machine](..\assets\images\postImg\230829JPAName\Machine.png)

사진에서 보면 pk가 num으로 지정되어 있다.
여기서 id는 그냥 id로 지정되어 있다.

In the picture above the num setted as a pk.
id is just id named in the DB.


# Problem  - 문제
Spring JPA의 findById 메소드를 사용하려고 하자... Id값을 찾아오지 못하는? 현상이 발생했다.

When I used JPA's findById method but It can't find value from the DB.


# Reason  - 원인
처음에 컬럼이름을 id로 지정했다. (PK로는 지정하지 않음)
findById 는 pk로 지정된 컬럼값을 가져오는 것인데 나는 pk가 아닌 컬럼이름 id의 값을 가져오고 싶었다.

I setted column name as id(but not pk)
Method findById is find pk Column value from the DB, but I wanted column name id's value (Not pk value)

# Conclusion
![Machine](..\assets\images\postImg\230829JPAName\query.png)

첫 번째로 일단 내 커스텀 쿼리를 만들기로했다. Machine Entity를 변경하기에는 수정해야하는 것이 많아서 일단은 이렇게 해결하기로 했다.

First I made my Custom Query. If I modified Machine Entity then I have to modify related files so I decide this way.

![Machine](..\assets\images\postImg\230829JPAName\for.png)
##### this is the usage!


![Machine](..\assets\images\postImg\230829JPAName\issue.jpg)
