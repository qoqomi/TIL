# [인프런] 제대로 파는 Git & GitHub-by yalco (2022.03)

**본 내용은 제대로 파는 Git&GitHub 강의를 토대로 작성하였습니다.**

## 1.CLI & GUI

- CLI(Command Line Interface) :명령줄 입력하여 사용
- GUI(Graphical User Interface)

## 2. Terminal 최초설정

- 터미널 프로그램에서 아래 명령어 실행 <br>
  `git --version` <br>
  `git config --global user.name "(본인 이름)"`<br>
  `git config --global user.email "(본인 이메일)"`<br>
- 아래의 명령어들로 확인
  `git config --global user.name`<br>
  `git config --global user.email`<br>

## 3. 프로젝트 생성 & Git 관리 시작

- 원하는 이름을 가진 폴더를 생성하고 VScode로 시작한다.
- 해당 폴더에서 (VSCode 터미널 기본) 아래 명렁어 입력한다. <br>
  `git init`
- 폴더에 숨김모드로 .git 폴더 생성 확인

> `.git` 폴더를 지우면 git내역이 삭제됨
> 맥에서 숨김파일보기 : `commend`+`shift`+`m`

- 해당 파일을 관리할까요 ?
  `git status`

## 4. Git에게 맡기지 않아야 할 것들

### Git의 관리에서 특정 파일/ 폴더를 배제해야 할 경우

1. 포함할 필요가 없을 때
   - 자동으로 생성 또는 다운로드되는 파일들(빌드 결과물, 라이브러리)
2. 포함하지 말아야 할 때
   - 보안상 민감한 정보를 담은 파일

### `.gitignore` 폴더 생성

1. `gitignore` 파일을 생성
2. `git status`로 명렁어 상태 확인

### `.gitignore` 형식

[형식 사이트](https://git-scm.com/docs/gitignore)

```
# 이렇게 #를 사용해서 주석

# 모든 file.c
file.c

# 최상위 폴더의 file.c
/file.c

# 모든 .c 확장자 파일
*.c

# .c 확장자지만 무시하지 않을 파일
!not_ignore_this.c

# logs란 이름의 파일 또는 폴더와 그 내용들
logs

# logs란 이름의 폴더와 그 내용들
logs/

# logs 폴더 바로 안의 debug.log와 .c 파일들
logs/debug.log
logs/*.c

# logs 폴더 바로 안, 또는 그 안의 다른 폴더(들) 안의 debug.log
logs/**/debug.log
```

# Reference

[인프런- 제대로 파는 Git & GitHub - by 얄코](https://www.inflearn.com/course/%EC%A0%9C%EB%8C%80%EB%A1%9C-%ED%8C%8C%EB%8A%94-%EA%B9%83/dashboard)
