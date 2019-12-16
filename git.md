



## Git 기초

### 0.준비 사항

[git bash](https://gitforwindows.org/)

* git 활용하기 위한 CLI(Command Line Interface)를 제공한다.
* source tree.github desktop 등을 통해 Gui환경에서도 활용이 가능하다.



##  1.로컬저장소 활용하기

----

### 1.저장소 초기화

```bash
$git init
Initialized empty Git repository in C:/Users/student/Desktop/TIL/.git/
```



* 저장소를 초기화하게 되면 .git폴더가 해당 리렉토리에 생성된다.
* bash상에서는 master라고 표기된다.
  * 현재 브렌치가 master라는 것을 의미한다.

### 2.add - straging area

git으로 관리되는 파일들은 Working directory(작업환경), Stranging Area, commit단계를 거쳐 이력에 저장된다.

```bash

$git add a.txt #파일명
$git add images #폴더명
$git add.#현재 디렉토리의 모든 파일 및 폴더


```



add 전 상태

```bash
$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        Markdown.md
        git.md
        image/

nothing added to commit but untracked files present (use "git add"


```

```bash
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   Markdown.md
        new file:   git.md
        new file:   image/20191103221129_fgyjnwts-1576470876663.jpg
        new file:   image/20191103221129_fgyjnwts.jpg


```



###  3.commit

> 커밋은 코드의 이력을 남기는 광정이다.

```basg
$ git commi -m [커밋 메세지]
$ git commit -m`마크다운`
bash: 마크다운: command not found
error: switch `m' requires a value

```

* 커밋 메세지는 항상 해당 이력에 대한 정보를 담을수 있도록 작성하는 것이 좋다
* 일관적인 커밋메세지를  작성하는  습관을 들인다.
* 이력 확인을 위해서는 아래의 명령어를 활용한다.



```bash
$ git log
commit aff64c63ce1b7bd9cc3e70d06876159ef3524be7 (HEAD -> master)
Author: rhkddl2422 <poon995@naver.com>
Date:   Mon Dec 16 14:28:17 2019 +0900

    이력확인을 위해서는 아래의 명령어를 입력한다.

```



**항상 status 명령어를 통해 git의 상태를 확인하자! commit 이후에는 log명령어를 통해 이력들을 확인하자!**

## 원격저장소 활용하기

> 원격저장소를 제공하는 서비스는 다양하게 존재한다. 
>
> 우리는 github를 기준으로 설명한다.

### 0.준비하기

* Github에서 저장소 생성



## 1.원격 저장소 설정

```bash
$ git remote add origin {github url}
```

* {github url} 부분에는 원격 저장소 url을 작성한다
* 원격저장소로{github url}을 origin이라는 이름으로 추가(add)하는 명령어이다.
* 원격저장소 목록을 보기 위해서는 아래의 명령어를 활용한다.

# 

```bash
$git remote -v
origin  https://github.com/rhkddl2422/TIL.git (fetch)
origin  https://github.com/rhkddl2422/TIL.git (push)


```

 

## 2. push

.	

```bash
$ git push origin master
```



* 설정은 원격저장소(origin)으로 push

폴더의 내용을 수정 및 삭제 생성등을 하게된다면 add,remote명령어를 통해서 이력을 저장하고 push명령어를 통해 업로드 한다.