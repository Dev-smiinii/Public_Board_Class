# 1단계 - Create a new repository & Tutorial Directory 및 파일 생성하기
1. 생성 시 기입/선택 대상 처리하기
   - 1. Repository name 기입: Public_Board_Class
   - 2. Description 기입: Public_게시판 수업 내용
   - 3. Public 선택
   - 4. Create repository 선택


2. create a new repository on the command line 참고하여 CLI 입력하기
```sh
$ cd ~
  # [cd] WSL로 /home 내부의 사용자 계정 Directory로 이동한다.

$ mkdir Public_Board_Class
  # [mkdir] WSL로 Public_Board_Class D를 생성한다.

$ cd Public_Board_Class
  # [cd] WSL로 Public_Board_Class D로 이동한다.
    # D명 입력 시 TAB 사용으로 자동 입력 기능을 사용할 수 있다.

$ echo "# Public Board Class" >> README.md
  # [echo] WSL로 README.md 파일을 간단히 만든다.

$ vi README.md
  # [vi & i] README.md 파일을 열고 'Public_게시판 수업 내용 단계별 정리' 내용 추가하기.
  # [ESC & :wq!] 추가된 내용 저장 후 README.md 파일 종료하기.

$ cat README.md  
  # [cat] WSL화면에서 README.md 파일의 내용을 텍스트로 확인한다.

$ git init
  # [init] WSL로 Public_Board_Class D에서 `git init`을 수행하여 '.git' D를 생성한다.
    # 1. Initialized empty Git repository in /home/sm/Public_Board_Class/.git/
    ## '.git' Directorty 생성의 의미: 해당 Directory가 git에 의해 관리될 것임을 명시함.
    ## 화살표가 노란색으로 변경됨.
       ## 노란색 화살표의 의미: Working Directory와 Repository가 상이한 상태임을 의미함.

$ git status
  # [status] WSL로 해당 시점의 관리 내역을 확인한다.
    # 1. On branch main
    # 2. No commits yet
    # 3. Untracked files:
    #      (use "git add <file>..." to include in what will be committed)
    #            README.md
    # 4. nothing added to commit but untracked files present (use "git add" to track)

$ git add README.md
  # [add] 첫 번째 Working Directory -> Staging Area로 이동시킨다.
    ## add 단계에서는 파일명을 명시해줘야 함.
    ## 화살표가 +로 변경됨.
       ## + 화살표의 의미: SA에 추가된, commit 대상이 있는 상태임을 의미함.

$ git status
  # [status] WSL로 해당 시점의 관리 내역을 확인한다.
    # 1. On branch main
    # 2. No commits yet
    # 3. Changes to be committed:
    #      (use "git rm --cached <file>..." to unstage)
    #            new file:   README.md

$ git commit -m "git init(first) commit"
  # [commit] 첫 번째 Staging Area -> Repository로 이동시킨다.
    # 1. [main (root-commit) c5cbcc6] git init(first) commit
    # 2.  1 file changed, 2 insertions(+)
    # 3.  create mode 100644 README.md
  # 노출될 메시지의 내용: git init(first) commit
    ## commit 단계에서는 파일명 대신 메시지의 내용을 명시해줘야 함.
       ## SA에 이미 들어와있는 변경 사항이 있는 파일들을 Repo로 이동시키는 것이기에 파일명을 기입하지 않음.
    ## 화살표가 노란색에서 초록색으로 변경됨.
       ## 초록색 화살표의 의미: WD와 RP가 동일한 상태임을 의미함.

$ git status
  # [status] WSL로 해당 시점의 관리 내역을 확인한다.
    # 1. On branch main
    # 2. nothing to commit, working tree clean

$ git branch -M main
  # [branch -M] 기본 branch를 main으로 지정하여 생성한다.

$ git remote add PBB https://github.com/Dev-smiinii/Public_Board_Class.git
  # [remote] 로컬 RP와 원격 RP를 연결한다.
    ## 'origin'은 원격 RP의 이름에 해당하지만 단순히 명칭에 불과하기에, 임의의 명칭인 'PBB'로 변경할 수 있다.
    ## 변경한 명칭으로 추후 push와 pull command를 입력해야 한다.

$ git push -u PBB main
  # [push] 로컬 RP에서 관리되고 있는 commit을 원격 RP로 전송한다.
    # 1. Enumerating objects: 3, done.
    # 2. Counting objects: 100% (3/3), done.
    # 3. Delta compression using up to 12 threads
    #    Compressing objects: 100% (2/2), done.
    # 4. Writing objects: 100% (3/3), 292 bytes | 292.00 KiB/s, done.
    # 5. Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
    #    To https://github.com/Dev-smiinii/Public_Board_Class.git
    # 6.  * [new branch]      main -> main
    #    Branch 'main' set up to track remote branch 'main' from 'PBB'.
    ## 중요! 해당 시점까지 진행되어야 Github에서 Commit History을 볼 수 있게된다. 
  ## push command 관련 참고 사항
     # 1. <Default> git push REMOTE-NAME BRANCH-NAME
     # 2. <Rename> git push REMOTE-NAME LOCAL-BRANCH-NAME:REMOTE-BRANCH-NAME
     # 3. <Delete> git push REMOTE-NAME :BRANCH-NAME

$ git status
  # [status] WSL로 해당 시점의 관리 내역을 확인한다.
    # 1. On branch main
    # 2. Your branch is up to date with 'PBB/main'
    # 3. nothing to commit, working tree clean
```

3. Tutorial Directory 및 파일 생성하기
```sh
$ mkdir Tutorial
  # [mkdir] WSL로 Public_Board_Class/Tutorial D를 생성한다.

$ cd Tutorial
  # [cd] WSL로 Public_Board_Class/Tutorial D로 이동한다.

$ vi Tutorial_1단계.md
  # [vi & i] Tutorial_1단계.md 파일을 생성 & 열고, '1단계에 해당하는 내용 일체' 내용 추가하기.
  # [ESC & :wq!] 추가된 내용 저장 후 Tutorial_1단계.md 파일 종료하기.
    ## 화살표가 노란색으로 변경됨.
       ## 노란색 화살표의 의미: Working Directory와 Repository가 상이한 상태임을 의미함.

$ git checkout -b Tutorial HEAD
  # [checkout -b] Tutorial branch를 생성과 동시에 선택하여 현재 branch 변경(HEAD 위치)시키기.

$ git add .
  # [add] WD -> SA로 이동시킨다.
    ## 파일명 대신 . 으로 전체 사항을 지정할 수 있음.
    ## [reset] add 취소하기로 SA -> Unstaged로 이동시킬 수 있음.
       ## "git reset HEAD <file>..." to unstage
    ## [restore] add 취소하기로 SA -> Unstaged로 이동시킬 수 있음.
       ## "git restore --staged <file>..." to unstage

$ git status
  # [status] WSL로 해당 시점의 관리 내역을 확인한다.
    # 1. On branch Tutorial
    # 2. Changes to be committed:
    #      (use "git restore --staged <file>..." to unstage)
    #            new file:   "Tutorial_1\353\213\250\352\263\204.md"

$ git commit -m "feat: Tutorial_1단계.md 파일 추가"
  # [commit] SA -> RP로 이동시킨다.
    # 1. [Tutorial b786c3e] feat: Tutorial_1단계.md 파일 추가
    # 2.  1 file changed, 202 insertions(+)
    # 3.  create mode 100644 "Tutorial/Tutorial_1\353\213\250\352\263\204.md"
  # 노출될 메시지의 내용: feat: Tutorial_1단계.md 파일 추가
    ## commit 단계에서는 파일명 대신 메시지의 내용을 명시해줘야 함.
       ## SA에 이미 들어와있는 변경 사항이 있는 파일들을 Repo로 이동시키는 것이기에 파일명을 기입하지 않음.
    ## [commit --amend] 직전 commit 한정 취소하기로 commit의 노출될 메시지를 변경할 수 있음.
       ## "git commit --amend"
    ## 화살표가 노란색에서 초록색으로 변경됨.
       ## 초록색 화살표의 의미: WD와 RP가 동일한 상태임을 의미함.
    ## [reset] commit 취소하기로 RP -> Unstaged로 이동시킬 수 있음.
       ## "git reset HEAD^"

$ git status
  # [status] WSL로 해당 시점의 관리 내역을 확인한다.
    # 1. On branch Tutorial
    # 2. nothing to commit, working tree clean

$ git push PBB Tutorial
  # [push] 로컬 RP에서 관리되고 있는 commit을 원격 RP로 전송한다.
    # 1. Enumerating objects: 5, done.
    # 2. Counting objects: 100% (5/5), done.
    # 3. Delta compression using up to 12 threads
    #    Compressing objects: 100% (3/3), done.
    # 4. Writing objects: 100% (4/4), 2.43 KiB | 2.43 MiB/s, done.
    # 5. Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
    #    remote:
    #    remote: Create a pull request for 'Tutorial' on Github by visiting:
    #    remote:      https://github.com/Dev-smiinii/Public_Board_Class/pull/new/Tutorial
    #    remote:
    #    To https://github.com/Dev-smiinii/Public_Board_Class.git
    # 6.  * [new branch]      Tutorial -> Tutorial

$ git status
  # [status] WSL로 해당 시점의 관리 내역을 확인한다.
    # 1. On branch Tutorial
    # 2. nothing to commit, working tree clean

$ git tag 1st_Tutorial/Fin
  # [tag] WSL로 로컬 RP의 해당 시점에 영구적인 포인터를 생성한다.
  ## tag command 관련 참고 사항
     # 1. <Default> git tag TAG-NAME
     # 2. <Delete> git tag -d TAG-NAME

$ git push PBB 1st_Tutorial/Fin
  # [push] WSL로 원격 RP의 해당 시점에 영구적인 포인터를 생성한다.
    # 1. Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
    # 2. To https://github.com/Dev-smiinii/Public_Board_Class.git
    # 3.  * [new tag]         1st_Tutorial -> 1st_Tutorial/Fin
  ## push command 관련 참고 사항
     # 1. <Tag> git push REMOTE-NAME TAG-NAME
     # 2. <All Tags> git push REMOTE-NAME --tags
     # 3. <Delete> git push --delete REMOTE-NAME TAG-NAME

$ git pull PBB Tutorial
  # [pull] 원격 RP에서 관리되고 있는 commit을 로컬 RP로 가져온다.
    # 1. From https://github.com/Dev-smiinii/Public_Board_Class
    # 2.  * branch            Tutorial   -> FETCH_HEAD
    # 3. Already up to date.
```
