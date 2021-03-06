# ifp-2022-team2
2022 IFP동아리 team2입니다.

-------------------------------------------------------------------------------------------------------------

## Tip

    다시 생각해 볼 겸 udemy로 배운걸 공유하기 위해 정리해봤습니다.

    오류나 추가사항에 대해 수정 환영합니다. 참고가 필요할 때 도움이 되면 좋겠습니다.

    + 이 readme는 markdown 문서로 github 블로그 사용 시 항상 다뤄야 하는 문서입니다.
    이 글을 수정한 저는 markdown 명령어를 모릅니다.. ㅎㅎ


    git 개념적인 부분은 검색하시면 좀 더 자세히 나올 겁니다.

    간단히 보면

        클라우드 (github)
    ----------------------- 별개 -------------------------
        ^업/다운 <-> 로컬 [ (.git 통괄) - commit 작업 ]

        commit 작업
        파일 작업 -> add 로 on stage -> commit

상세 참고 : https://git-scm.com/docs


github repository 생성 시 readme.me 생성하고 만들어 놓으면 main brunch로 생성됩니다.. 아예 빈 repo로 생성하면
처음으로 push하는 brunch명으로 brunch 생성됩니다 이때 bash 유저면 clone을 사용하지 않고 추후 git에서 remote로 커밋 시
github는 main으로 git은 master로 이 상태인줄 모르고 커밋하면 브랜치가 2개가 됩니다. git에서 브랜치를 main으로 만들고 
커밋하면 상관은 없지만 혹시 몰라서 써놓습니다.


### github의 파일을 로컬환경에서 사용할 때
미세팁
git bash 설치 시 vscode로 편집 설정 시 git에서 리눅스처럼 vim과 같은 편집기 대신 vscode로 편집할 수 있도록 설정할 수 있다.
git bash 설정에서 사용가능 
- 이 편집기 사용 할 일이 종종 나타날 수 있다. branch merge나 커밋 reset등 기존 커밋 수정이나 
브랜치 합병 시 해당 파일의 수정된 사항과 기존 유지 사항에 대해 편집기로 수정해야한다.

git global 계정을 정해주어야 하는데 
git config --global user.name "유저명" : git 유저명
git config --global user.email "github 이메일" : git 유저 계정


다운하고 파일을 풀어서 사용할 때
 1. 그냥 다운로드하고 압축을 푸시면 git bash나 desktop으로 다룰때 해당 디렉토리에 git init 명령어로 로컬 git을 사용할
 준비를 합니다.
 
 이 상태는 github의 repo와 별개로 여기서 commit하는 파일들은 전부 로컬에서의 commit입니다.
 git 커밋은 

git을 통해 clone으로 사용할 때
 2. bash의 명령어의 경우로 (desktop은 안써봐서 잘 모릅니다.) clone을 통해 repo를 가져올 수 있습니다.
 github의 code에서 http 또는 ssh(설정필요) url 복사 후
 bash의 창에
 $ git clone 복사한_repo_url 을 입력하시면 bash가 있는 디렉토리
  - [ 만약 bash를 열자마자 사용하면 c:user/user명 폴더가 ~ (리눅스로 치면 root 디렉토리) 로 설정되어 있습니다.
    개인적으로 사용하는 프로젝트용 디렉토리가 있다면 해당 디렉토리로 cd /"~~~ 디렉토리 경로" 이동해서 사용하면 됩니다.
    경로 이동 시 해당 위치 폴더에서 우클릭으로 경로복사를 해도 되고, 파일 탐색기 위의 경로에서 복사해와도 됩니다. ]
    항상 git bash를 켜면 ~ 위치로 .git이 있는 프로젝트 파일로 이동해야 사용가능합니다.

    +ex - cd c:/user/user명/downloads | cd d:/project 등 
        -> 가끔 cmd 등에서 cd d:/... 로 경로설정해도 경로가 이동된 걸로 보이지 않는 경우도 있는데 
        이때 d: (드라이브 라벨) 만 쳐도 보입니다.

    cd 등 리눅스 명령어들 중 가끔이나 자주 쓴다고 생각한 것들
        cd 사용 시 { ./ 해당 디렉토리 내 } { ../ 해당 디렉토리 이전 디렉토리 내 }
        내가 d:/hello/world 디렉토리 안이라면 ./ 는 d:/hello ../ 는 d:

        - cd /파일명 으로 에러 시 ./파일명 하면 바로 됩니다.

        ls, dir : 해당 디렉토리 내 파일과 디렉토리 확인 시 ls는 dir과 달리 디렉토리인지 아닌지 구분되도록 표시됩니다.

        pwd : 현재 위치의 디렉토리 경로 출력

        touch "파일명.확장자명" : 잘 사용은 하지 않을 듯 하나 txt, py 등 파일명.확장자명으로 워드 파일도 만들 수 있다. 1.docx

        rm -rf : 파일 삭제인데 뒤 옵션은 강제 삭제로 아예 지워버리므로 rm만 사용해서 지우는게 좋습니다.


로컬에서 git을 사용할 때
1. git을 사용할 폴더의 디렉토리로 이동합니다.
2. 해당 디렉토리에서 git status로 .git 파일이 있는지 확인합니다. - fatal 에러가 나와야 정상입니다.
3. git init을 통해 .git 생성 사용할 준비 끝입니다. 
    만약 .git파일이 해당 디렉토리 내 파일 중 존재한다면 .git 파일을 그냥 지워버리면 끝입니다.

로컬에서 github로
github -> 로컬 시 clone과 파일 다운 후 사용 2가지로 알고 있습니다.

로컬 -> github
1. github에서 빈 repo 만들고 clone하기

2. clone이 아닌 기존에 작업 중이던 프로젝트를 업로드하고 싶다면
    1. 해당 git 폴더로 이동
    2. git remote add origin github_repo_복사url : origin은 정확히 remote한 url의 별칭입니다. 마음대로 정하셔도 됩니다.
        나중에 remote 해놓은 url에 대해 알아야 한다면 git remote 입력 시 등록했던 별칭이 보입니다.
    3. git push origin master 또는 git push -u origin master : 저기서 origin 대신 github repo url로 입력해도 됩니다.
        git push remote별칭명 브랜치명 으로 입력하며 2번째 명령어의 -u 설정은 기본 push를 같은 url로 유지하겠다는 뜻입니다.

        git push 시 지금까지 commit 했던 파일만 올라가므로 add, commit 하지 않은 파일은 업로드 되지 않습니다.


.gitignore : git commit 시 데이터 파일이나 용량이 큰 라이브러리가 굳이 github로 업로드나 commit 될 필요가 없는 경우가 있습니다.
이때 해당 파일을 생성하고 파일 내에 .확장자명 /디렉토리명 등을 통해 해당 파일들을 업로드하지 않을 수 있습니다.
 - 문서 참고해주세요 : git ignore 목록에 대해 작성된 온라인 문서 확인.


### git 사용 시 명령어
명령어들의 옵션은 git 명령어 -h 를 통해 확인 후 추가적으로 사용하거나 검색을 통해 필요할 때 사용하시면 되겠습니다.
tab을 사용하면 디렉토리 내 파일이 빠르게 작성됩니다. tab 아주 유용하게 씁니다. 

상태확인 시작 명령어
git status : git의 변경파일과 stage 된 파일에 대해 알 수 있습니다.

git init : 디렉토리에 git 작업을 위한 환경을 구성해줍니다.

git log : 지금까지 commit 혹은 branch 변경을 통해 작업한 내용들을 보여줍니다. q 로 나갈 수 있습니다.
    git log --oneline : log를 한줄로 간단하게 만들어 줍니다.

파일 stage(추가, 업로드), commit 명령어
git add : . 으로 모든 변경사항에 대해 stage합니다. 
파일명 파일명 파일명 ... 으로 띄어쓰기로 구분해서 파일명을 작성 시 원하는 파일만 stage 할 수 있습니다.

git commit -m "커밋 메세지" : stage 된 파일을 실질적으로 저장 등록합니다. commit 없이 add만으론 파일이 작업에
기록된게 아닙니다. 커밋 메세지는 작업자가 구분을 위해 전달하는 메세지로 변경사항에 대해 작성하면 됩니다.
    -am 옵션 시 모든 변경사항을 add 없이 바로 작성 가능합니다.

    git commit 시 등록된 편집기로 commit 메세지를 작성하면 됩니다. 작성 후 닫으면 바로 commit 됩니다.

브랜치 명령어
git checkout : 예전의 명령어로 brach 생성 이동 undo(작업내용 되돌리기) 등등 많은 기능을 담당했으나 
이젠 여러 명령어로 나뉘어졌습니다.

git branch -옵션 "브랜치명" : 브랜치 생성. 추가 브랜치는 이전 브랜치의 브랜치 생성 명령어 입력 당시의 커밋을
기준으로 새로운 작업을 진행할 수 있는 새로운 작업공간입니다. 브랜치 변경 후 작업 이후 다시 기존의 브랜치로
돌아가면 새로운 브랜치에서 작업한 내용이 없는 것을 확인할 수 있습니다.
    -v : 브랜치 정보
    -d : 브랜치 삭제
    -m : 브랜치명 변경 - 해당 브랜치에 위치해야 변경가능

git switch -옵션 "브랜치명" : 브랜치 이동, 생성도 가능 생성된 브랜치로 이동가능하고 브랜치를 생성도 할 수 있습니다.
    -c : 브랜치 생성

### 사용 시 주의 상세히 검색하고 유의해서 사용바랍니다.
git merge "병합 할 branch명" : 병합될 브랜치로 이동 후 사용. 작업 내용을 기존 branch로 옮깁니다.
만약 기존 branch에서 추가 commit이 없다면 merge 시 fast-forward 라는 명령어로 병합이 바로 이루어집니다.

commit 복구 명령어

git checkout HEAD~숫자 - 또는 해쉬코드 : HEAD물결숫자 시 제일 최근 커밋을 기준으로 숫자만큼 과거의 커밋에 대해 돌아갑니다.
해쉬코드는 git log 시 앞 7자리, git log --oneline 시 7자리에 대해 입력하면 해당 커밋으로 돌아갑니다.

git restore "파일명" : --source HEAD~2...n 번째 파일명 해당 파일의 commit을 복구 해쉬코드도 사용가능합니다.

-ex git restore --source HEAD~2 add.py | git restore --source e7f540a add.py
    checkout도 마찬가지

다른 브랜치에서 작업 후 위의 명령어 사용 시 detached head라는 에러같은 메세지가 나타나는데 해당 복구로 인해 현재 브랜치의 HEAD
인 위치와 복구로 인한 HEAD 위치가 다르다는 뜻이므로 새로운 브랜치를 생성하고 옮긴 뒤 commit하면 문제가 사라진다.
 - 사용 시 반드시 검색을 통해 확인해주세요 배울 때 이렇게 배우긴 했는데 좀 불확실 하네요. 제대로 동작하면 다행입니다.

    --staged 를 통해 add로 스테이지된 파일을 다시 언스테이지 할 수 있습니다. git add 시 bash에서 제안합니다.

git reset 해쉬코드 : 해쉬코드로 커밋의 위치로 복귀하는데 HEAD를 기준으로 해쉬코드 커밋까지 전부 사라집니다. 

    --hard commit --HEAD~2....5 : 위와는 다르게 커밋을 전부 없애고 복귀합니다. 브랜치는 유지됩니다.

git revert 해쉬코드 : 새로운 커밋을 하고 복구시킵니다. 이 작업 시 충돌이 일어납니다. 기존과 현재 
파일의 상태가 다르기 때문에 변경사항 중에서 직접 지우고 추가하는 작업을 해야합니다.

클라우드 명령어
git clone url링크 : github 뿐만 아니라 다른 url로 클라우드 시스템을 제공하는 다른 프로젝트에 대해서도 사용가능합니다.

git remote add 별칭명 url링크 : 다운받거나 추가적으로 업로드 시 사용되는 별칭 생성을 위한 명령어

git push -옵션 별칭명 브랜치명 : 로컬에서 작업한 내용을 업로드 하는 기능으로 commit한 내용만 github로 업로드 됩니다.
    -u : push의 default로 1번 사용하면 다음부턴 git push로만 간단하게 업로드 가능합니다.

git pull 별칭명 : github에 변경사항이 업로드 되었을때 다운받을 수 있는 명령어 입니다. 변경사항이 없으면 다운로드도 없습니다.


=========================================================================================================

git과 github에 대해 잘 모르거나 사용법을 잘 모를때, 기억이 나지 않을 떄 참고하면 좋을 것 같습니다. 
완전 자세한 설명서는 아닙니다.


저도 복구 명령어와 브랜치 자체는 자주 사용 해볼 일이 없어서 상세히는 모릅니다.. 그러므로 작업 오류로 사용하게 되면
사용 시 꼭 주의하고 사용하기 바랍니다. 작업이 전부 사라져 버릴 지도 모릅니다.

그래도 branch 와 복구 기능을 잘 사용하면 매우 유용한건 확실했기 때문에 연습하고 사용하면 좋겠습니다.
