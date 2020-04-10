# Git

>  분산형 버전관리 시스템 (DVCS)  // Commit 으로 version관리

[다운로드](**https://gitforwindows.org/**)

## Github

> Git의 원격 저장소  // Gitlab, Bitbucket



## Git 기초 명령어

폴더를 열고 폴더에서 git bash here 클릭

### 1. 저장소 설정

```bash
# 텍스트 파일 생성
$ touch xxx.txt
# 폴더 안 list
$ ls

# git 환경 초기화
$ git init
# 폴더 디렉토리 옆에 (master) 생성
Initialized empty Git repository in C:/Users/gw130/Desktop/git_연습/.git/

# git hub 연결 아이디와 email연결
git config --global user.name gw1303
git config --global user.email gw1303@nate.com
```



### 2. 파일 올리기

```bash
# 작업공간 (WD)
    |
$ git add
    |
# 스테이지 (Staging Area)
    |
$ git commit -m '커밋 메시지(버전)'
[master (root-commit) 15683e1] 커밋 메시지(버전)
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 cli.txt

# 커밋 이력을 확인
$ git log

commit 15683e1530682f37c89c94a7d49ca58e90f84ba4 (HEAD -> master)
Author: gw1303 <gw1303@nate.com>
Date:   Fri Apr 10 10:26:59 2020 +0900

    커밋 메시지(버전)

$ git push

```

- 스테이지에 추가

  ```bash
  $ git add a.txt     # 파일 단위
  $ git add myfolder/ # 폴더 단위
  $ git add .         # 전체
  ```

- 추가 후 상태

  ```bash
  $ git status
  On branch master
  
  No commits yet
  
  Changes to be committed:
    (use "git rm --cached <file>..." to unstage)
          new file:   cli.txt
  
  ```

- 커밋 상태 확인

  ```bash
  $ git log
  $ git log -1            # 최근 한 개 커밋
  $ git log --oneline     # 간략한 로그
  $ git log --oneline -1  # 최근 한 개의 커밋을 간략하게
  ```

- restore

  ```bash
  # 스테이지에 올린 파일을 제거
  $ git restore --staged <file>...
  
  
  ```

  

## 원격 저장소 관리(Git hub)

![image-20200410112148951](C:\Users\gw130\AppData\Roaming\Typora\typora-user-images\image-20200410112148951.png)



