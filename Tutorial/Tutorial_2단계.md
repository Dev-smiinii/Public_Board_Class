# 2단계 - WSL만을 사용한 기본 Directory 만들기
1. main branch로 이동하기 & Public_Board_Class D로 이동하기
```sh
$ git checkout main
  # [checkout] main branch를 선택하여 현재 branch 변경(HEAD 위치)시키기.

$ cd ..
  # [cd] WSL로 Public_Board_Class D로 이동한다.
    # D명 입력 시 .. 사용으로 직전 상위 D로 이동할 수 있다.
```


2. [mkdir] WSL로 기본적인 D 구조를 만든다.
```sh
$ mkdir board public
  # 1. Public_Board_Class\board
  # 2. Public_Board_Class\public

$ mkdir -p public/css public/images public/js/board public/js/lib
또는
$ mkdir -p public/{css,images} public/js/{board,lib}
  # 3. Public_Board_Class\public\css
  # 4. Public_Board_Class\public\images
  # 5. Public_Board_Class\public\js\board
  # 6. Public_Board_Class\public\js\lib
  ## mkdir command 관련 참고 사항
     # 1. <Default> mkdir DIRECTORY-NAME
     # 2. <Multiple> mkdir DIRECTORY-NAME DIRECTORY-NAME
     # 3. <Depth> mkdir -p DIRECTORY-NAME/DIRECTORY-NAME
     # 4. <Depth & Multiple> mkdir -p DIRECTORY-NAME/{DIRECTORY-NAME,DIRECTORY-NAME}
     # 5. <Authority> mkdir -m 777 DIRECTORY-NAME
```


3. [mv] WSL로 디렉토리의 이름을 수정한다.
```sh
$ mv board/ board_html/
  # 1. Public_Board_Class\board -> Public_Board_Class\board_html

$ mv public/js/board/ public/js/board_js/
  # 2. Public_Board_Class\public\js\board -> Public_Board_Class\public\js\board_js
  ## mv command 관련 참고 사항
     # 1. <Default> mv FILE-NAME FILE-NAME
     # 2. <Directory> mv DIRECTORY-NAME/ DIRECTORY-NAME/
```


4. 변경 사항을 만들어 commit을 추가 및 처리한다.
```sh
$ vi README.md
  # [vi & i] README.md 파일을 열고 각 열에 'Branch: main, Tutorial', 'Tag: 1st_Tutorial/Fin' 내용 추가하기.
  # [ESC & :wq!] 추가된 내용 저장 후 README.md 파일 종료하기.

$ git add .
  # [add] WD -> SA로 이동시킨다.

$ git commit -m "docs & feat: WSL만을 사용한 기본 Directory 만들기"
  # [commit] SA -> RP로 이동시킨다.

$ git tag 1st_WSL/Fin
  # [tag] WSL로 로컬 RP의 해당 시점에 영구적인 포인터를 생성한다.

$ git push PBB 1st_WSL/Fin
  # [push] WSL로 원격 RP의 해당 시점에 영구적인 포인터를 생성한다.

$ git push PBB main
  # [push] 로컬 RP에서 관리되고 있는 commit을 원격 RP로 전송한다.

$ git pull PBB main
  # [pull] 원격 RP에서 관리되고 있는 commit을 로컬 RP로 가져온다.
```


5. Tutorial branch로 이동하기 & Public_Board_Class D로 이동하기
```sh
$ git checkout Tutorial
  # [checkout] Tutorial branch를 선택하여 현재 branch 변경(HEAD 위치)시키기.

$ cd Tutorial
  # [cd] WSL로 Public_Board_Class\Tutorial D로 이동한다.

$ vi Tutorial_2단계.md
  # [vi & i] Tutorial_2단계.md 파일을 생성 & 열고, '2단계에 해당하는 내용 일체' 내용 추가하기.
  # [ESC & :wq!] 추가된 내용 저장 후 Tutorial_2단계.md 파일 종료하기.

$ git add .
  # [add] WD -> SA로 이동시킨다.

$ git commit -m "feat: Tutorial_2단계.md 파일 추가"
  # [commit] SA -> RP로 이동시킨다.

$ git tag 2nd_Tutorial/Fin
  # [tag] WSL로 로컬 RP의 해당 시점에 영구적인 포인터를 생성한다.

$ git push PBB 2nd_Tutorial/Fin
  # [push] WSL로 원격 RP의 해당 시점에 영구적인 포인터를 생성한다.

$ git push PBB Tutorial
  # [push] 로컬 RP에서 관리되고 있는 commit을 원격 RP로 전송한다.

$ git pull PBB Tutorial
  # [pull] 원격 RP에서 관리되고 있는 commit을 로컬 RP로 가져온다.
```