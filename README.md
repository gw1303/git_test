# 0410 Git 특강
## Git

>  분산형 버전관리 시스템 (DVCS)  // Commit 으로 version관리

[다운로드](**https://gitforwindows.org/**)

## Github

> Git의 원격 저장소  // Gitlab, Bitbucket



## Git 기초 명령어

폴더를 열고 폴더에서 git bash here 클릭

### 1. 저장소 설정 (init)

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

  

## 원격 저장소 활용 (Git hub)

### 원격 저장소 생성

![image-20200410113537284](C:\Users\gw130\AppData\Roaming\Typora\typora-user-images\image-20200410113537284.png)

### 1. 원격 저장소 설정

- 원격 저장소 설정

  ```bash
  $ git remote add origin https://github.com/gw1303/git_test.git
  
  # 원격저장소(remote)로 origin 이름으로 url을 추가(add)
  # 깃아 원격 저장소로 추가해줘 오리진이라는 이름으로 url을
  ```

- 원격 저장소 목록

  ```bash
  $ git remote -v
  
  origin  https://github.com/gw1303/git_test.git (fetch)
  origin  https://github.com/gw1303/git_test.git (push)
  ```

- 원격 저장소 삭제

  ```bash
  $ git remote rm origin
  
  # `origin` 이름의 원격 저장소 설정을 삭제(remove -rm)
  ```

  

### 2. 올리기 (Push)

```bash
$ git push -u origin master

# 현재 폴더를 그대로 업로드 하는 것이 아니라, 지금까지의 이력/버전(commit)을 push하는 것
# Working directory, Staging area의 변경 사항들은 원격 저장소로 push되지 않는다.
# 따라서, push전에 $git status, $git log를 통해서 확인하는 습관을 갖자!!
```



### 3. 내려받기 (Pull)

```bash
$ git pull origin master

# github 저장소에 올라가있는 가장 최신 버젼의 이력을 로컬 저장소로 불러온다.
```



### 4. 원격 저장소 데이터를 로컬로 복제하기(clone)

```bash
# url의 git 데이터 가져오기
$ git clone {__url__}

Cloning into 'git'...
remote: Enumerating objects: 19, done.
remote: Counting objects: 100% (19/19), done.
remote: Compressing objects: 100% (13/13), done.
remote: Total 19 (delta 4), reused 15 (delta 3), pack-reused 0
Receiving objects: 100% (19/19), 4.18 KiB | 1.04 MiB/s, done.
Resolving deltas: 100% (4/4), done.


# 디렉토리 변경
gw130@DESKTOP-V7R2S73 MINGW64 ~/Desktop/home
$ cd git

gw130@DESKTOP-V7R2S73 MINGW64 ~/Desktop/home/git (master)
```



## CVCS

> 중앙집중형처리

![Git VS Subversion](https://t1.daumcdn.net/cfile/tistory/184C803F514047D41D)

## DVCS

> 분산처리

![형상관리의 종류 "중앙집중식 버젼 관리 시스템 VS 분산형 버젼 관리 ...](https://t1.daumcdn.net/cfile/tistory/2511743F514047D442)



## CLI

> Command Line Interface에서는 명령어와  그 결과를 항상 주의하자.

1. `ls` - 디렉토리 목록

   ```bash
   $ ls
     a.txt   b.txt
   ```

2.  `cd` - 디렉토리 변경

   ```bash
   ~/Desktop/ $ cd image/
   ~/Desktop/image/ $ cd ..
   ~/Desketop/ $
   ```

   - `.` : 현재 디렉토리
   - `..` : 상위 디렉토리
   - `~` : 홈 디렉토리

3.  `pwd` - 현재 작업 디렉토리

   ```bash
   ~/Desktop/ $ pwd
   /C/Users/student/Desktop $
   ```



## VI (Vim)

> CLI 환경에서 쓸 수 있는 텍스트 에디터 중 하나
>
> : commit 하는 과정에서 메시지 옵션을 쓰지 않으면, 나타난다.

- 편집모드 : `i`
- 명령모드 : `esc`
  - `:wq` : 저장하고 종료



## 원격 저장소 활용 시 주의사항

> 원격 저장소의 이력과 로컬의 이력이 다른 경우 error
>
> --> 작업 전 pull을 하면 문제 해결 !





## Git 프로젝트 관리

### 1. .gitignore

> git 으로 관리하지 않고 싶은 파일 목록은 `.gitignore` 에 정의한다.

```bash
# vi로 작성해야 인코딩이 깨지지 않음
$ vi .gitignore
```

- .gitignore

  ```bash
  *.xlsx        # 특정 확장자
  secret.txt    # 특정 파일
  test/         # 특정 폴더
  ```

- 주의 : 확장자 없음

- 만얀, 어떤 파일을 일반적으로 등록하는지 모른다면 [http://gitignore.io/](gitignore.io) 에서 검색

  



















