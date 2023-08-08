---
layout: post
author: YellTa
title: "[git commit하는 방법] [How to commit to the git Repository]"
tags: [git]
categories: ["memo"]
---

## Table of Contents - 목차!

1. [What is Git 깃이 뭘까?](#what-is-git-깃이-뭘까)
2. [Git terms 깃 용어들](#git-terms-깃-용어들)
3. [Commit and Push 깃 커밋하고 푸쉬해보기](#commit-and-push-깃-커밋하고-푸쉬해보기)


---

# [What is Git 깃이 뭘까?](#what-is-git-깃이-뭘까)
여러명의 개발자가 하나의 소프트웨어 개발 프로젝트에 참여할 떄, 소스 코드를 관리하는데 주로 사용한다.

Use it to manage Project's source code, when several developers make one software.


# [Git terms 깃 용어들](#git-terms-깃-용어들)

### Repository (리포지토리) :
말 그대로 프로젝트가 저장되는 장소, 컴퓨터의 로컬 폴더가 될 수 있고 다른 온라인 호스트의 저장공간이 될 수도 있다. 저장소 안에 파일을 저장하고 이름을 붙일 수 있다.

Project's save location. It can be the local folder in your computer and the online host's location. we can name the Repository and save files. 

### version Control (버전관리) :
프로젝트 히스토리 모든 시점의 "스냅샷"을 유지해 프로젝트 버전관리를 한다.

Take a "snapshot" of the Project's history to the manage project's version.

### Commit(커밋) :
저장소에 "스냅샷"을 찍어, 프로젝트를 이전 상태로 돌릴 수 있는 체크 포인트를 가질 수 있다.

Take a snapshot in the Repository, so can roll back your project's history. It means we can make a savepoint for my project through git commit!


### branch(브랜치) :
메인 브랜치의 브렌치를 따와서(branch off), 자신이 변경하고 자신만의 버전을 만들고 작업이 끝나면 메인 디렉토리인 master에 브랜치를 다시 ***Merge***한다.

Branch Off from the main Branch, and make the custom version after finishing the process then ***Merge*** your own branch to the main branch. 

# [Commit and Push 깃 커밋하고 푸쉬해보기]

### background, 사전설정
우선 깃에 본인의 Repository가 설정되어 있다고 가정한다. Repository만드는 법은 다른 곳에 많이 있으니 스킵!
<br>First, you have to have your own Git Repository. The way of making Git Repository is on google!.


### git init
	G:[project location]> git init
	Reinitialized existing Git repository in G:[project location]/.git/


git init 을 통해서 이 디렉터리가 로컬 깃 저장소라고 지정한다.<br>
Make your project directory as a local git directory through **git init** command.



### git status
    G:[project location]> git status
    
    G:[project location]>git status
    On branch master #selected branch 
    Your branch is up to date with 'github/master'.

    Untracked files:
        (use "git add <file>..." to include in what will be committed)
        burgerputProject/
        mysql-8.0.33-winx64/

### git add [file or folder or *]
    git add *
위처럼 작성하면 폴더 안의 모든 내용을 **add** 하겠단 뜻이다.<br>
If write the command above then It means to add every file and folder to git.
    

### git status
    ...
    Untracked files:
        (use "git add <file>..." to include in what will be committed)
            gitCommit.txt
            mysql-8.0.33-winx64/
            
나의 경우에는 프로젝트 폴더를 업로드했다. 업로드한 파일은 초록색으로 표시된다.<br>
In my case I added my project folder. Added files makred green color.

### git commit
    git commit -m "message"
    
커밋할 때 주석을 달아서 커밋한다. 변경사항 같은 것을 간략히 표기하는 것이다.<br>
Commit with the note. Briefly write the changes.


## 로컬저장소와 깃허브 저장소 연결하기 Connect local Repository and online Repository

### git remote add "online name" \[git online address\]
    git remote add origin https://github.com/yellTa/burgerput.git
    
    G:[project location]>git remote -v
    
    github  https://github.com/yellTa/burgerput.git (fetch)
    github  https://github.com/yellTa/burgerput.git (push)
    origin  https://github.com/yellTa/burgerput.git (fetch)
    origin  https://github.com/yellTa/burgerput.git (push)
    

origin이라는 이름으로 이번에 새로 만들었다. 만약 변경을 위한다면!<br>
I made git remote named as "origin". If want to delete it 

    
    git remote remove github
    G:[project location]git remote -v
    
    origin  https://github.com/yellTa/burgerput.git (fetch)
    origin  https://github.com/yellTa/burgerput.git (push)
    
    
위의 커맨드를 사용하면 된다.<br>
Use it command above.

### git push --set-upstream origin master
    Enumerating objects: 5422, done.
    Counting objects: 100% (5422/5422), done.
    Delta compression using up to 8 threads
    Compressing objects: 100% (5296/5296), done.
    Writing objects: 100% (5421/5421), 95.08 MiB | 2.60 MiB/s, done.
    Total 5421 (delta 439), reused 0 (delta 0), pack-reused 0
    remote: Resolving deltas: 100% (439/439), done.
    To https://github.com/yellTa/burgerput.git
       f725290..4cee4f5  master -> master
    branch 'master' set up to track 'origin/master'.
    
    
origin에 master브랜치에 add한 항목을 추가한다.<br>
push Added file to master branch.

---
{: data-content="hr with text"}
#### references 참고자료들!
[깃헙 사용법 차근차근 첫 커밋 해보기](https://sudo-minz.tistory.com/10)<br>
[깃과 깃허브란 무엇인가?](https://yanacoding.tistory.com/4)


---

