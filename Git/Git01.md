# [인프런] 제대로 파는 Git & GitHub-by yalco (2022.03)

**본 내용은 제대로 파는 Git&GitHub 강의를 토대로 작성하였습니다.**

## 1.CLI & GUI

CLI(Command Line Interface) :명령줄 입력하여 사용
GUI(Graphical User Interface) : ekfm

## 2. Terminal 최초설정

- 터미널 프로그램에서 아래 명령어 실행
  `git --version`
  `git config --global user.name "(본인 이름)"`
  `git config --global user.email "(본인 이메일)"`
- 아래의 명령어들로 확인
  `git config --global user.name`
  `git config --global user.email`

## 3. 프로젝트 생성 & Git 관리 시작

- 원하는 이름을 가진 폴더를 생성하고 VScode로 시작한다.
- 해당 폴더에서 (VSCode 터미널 기본) 아래 명렁어 입력한다.
  `git init`
- 폴더에 숨김모드로 .git 폴더 생성 확인

> `.git` 폴더를 지우면 git내역이 삭제됨
> 맥에서 숨김파일보기 : `commend`+`shift`+`m`

- 해당 파일을 관리할까요 ?
  `git status`

# Reference

[인프런- 제대로 파는 Git & GitHub - by 얄코](https://www.inflearn.com/course/%EC%A0%9C%EB%8C%80%EB%A1%9C-%ED%8C%8C%EB%8A%94-%EA%B9%83/dashboard)
