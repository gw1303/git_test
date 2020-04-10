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
# 작업공간
    |
$ git add
    |
# 스테이지
    |
$ git commit

# commit 상태 확인
$ git log

$ git push

```

