## git setting 관련

#### code로 열기
1. git config --global core.editor "code --wait"
   -> git config --global -e : vscode로 열림
   (맥에서 간혹 code. / git "code"를 못 찾는 경우 application 디렉토리에 vscode를 넣어주면 된다

#### 명령어 hist로 로그 이쁘게 보기
2. git config --global alias.hist "log --graph --all --pretty=format:'%C(yellow)[%ad]%C(reset) %C(green)[%h]%C(reset) | %C(white)%s %C(bold red){{%an}}%C(reset) %C(blue)%d%C(reset)' --date=short"
    -> git 로그 이쁘게 보기


#### 메모장
<cmder에서 conemu 에러날때>
https://ngio.co.kr/7415

<config 관련>
git config --list : 깃 config 모든 셋팅 보여줌
git config --global -e : config를 에디터로 열어줌
git config --global core.editor "code --wait" : 에디터가 열려있으면 터미널은 wait 상태

<config setting 관련>
git config --global user.name "sumin" : setting
git config --global user.email "email" : setting
git config user.name
git config user.email

<auto CRLF 관련: 개행문자>
git config --global core.autocrlf true (window)
git config --global core.autocrlf input (mac)

<git Aliases : 깃 명령어 축소할 수 있는 기능>
git config --global alias.co checkout  : checkout -> co 변경함(checkout도 같이 쓸수 있음)
it config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status

<help>
git config --help
git config -h

<init>
git init :초기화
rm -rf .git : 깃 삭제

<status>
git status
git status -s

<gitignore>
vim .gitignore : 생성

*.a : .a 모든 파일 
!lib.a : # but do track lib.a, even though you're ignoring .a files above
/TODO : # only ignore the TODO file in the current directory, not subdir/TODO
build/ : # ignore all files in any directory named build
doc/*.txt : # ignore doc/notes.txt, but not doc/server/arch.txt
doc/**/*.pdf : # ignore all .pdf files in the doc/ directory and any of its subdirectories

<staging file>
git add a.txt
git add a.txt b.txt
git add *.txt
git add *
git add .

<modifying files>
rm file.txt : 삭제
git add file.txt
git rm file.txt
git rm --cached file.txt
git clean -fd

git mv from.txt to.txt
git mv from.text /logs/from.text

<viewing the changes>
git diff
git diff --staged
git diff --cached

<commit>
git commit : 에디터 오픈 (commit stagged files)
git commit -m : commit stagged files with commit message
git commit -am : commit all files with commit message

<history>
git log
git log --patch
git log -p
git log --state
git log --oneline
git log --oneline --reverse

<tag>
git tag v1.0.0
git tag v1.0.0 hash
git show v.0.0
git tag -a v0.0.0 -m
git tag -l "v1.0.*" : v1.0.*에 해당하는 태그 보여줌
git tag -d v1.0.0 : 삭제

git checkout v1.0.0 : 체크아웃
git checkout -b branchName v1.0.0 : 태그에 브렌치 생성

<branch>
git branch
git branch --all : github, gitlab과 같은 원격과 연결된 모든 브렌치 보여줌
git clone -b {브렌치명} --single-branch {브렌치 주소}
git checkout -b {브렌치명} : 브렌치 생성하면서 체크아웃
git branch -m {old} {new} : 브렌치 old를 new로 변경
git branch -d {브렌치명}

git branch -a : 모든 브렌치
git branch -r : 원격에 있는 브렌치만

<stash>
git stash push -m "message" : 현재 작업을 stash영역에 push
git stash : push랑 똑같음
git stash --keep-index : ??
git stash -u : untracked 된 작업물을 push함

git stash list : stash 리스트를 보여줌
git stash show hash : 해당 해쉬의 상태를 보여줌
git stash show hash -p : 해당 해쉬의 상태를 자세히 보여줌

git stash apply (hash) : 가장 최근꺼 꺼내오는거(hash 꺼내오는거)
git stash apply --index : 
git stash pop : stash pop
git stash branch branchName : 

git stash drop hash : 해당 해쉬 삭제
git stash clear : stash 다 삭제


<undo>
협업 중이라면 신중하게 undo 해야함, 이 기능은 git 서버에 아직 push하지 않았을때 사용하는게 좋다
github, gitlab과 같은 서버로 협업을 하고 있다면 미리 undo 상황을 정리하고 push 할 수 있다.

git commit --amend -m "." : 커밋 메세지 변경
git commit --amend : 커밋한 파일의 내용을 수정했을때

<Reset>
git reset --mixed : 초기화하면서 working directory로 가져오는것
git reset --soft HEAD~2: 초기화 하면서 staging area로 가져오는것
git reset --hard HEAD

git reset HEAD~2: HEAD에서 두번째에 있는 커밋으로 포인터를 옮김

git reset --hard hash : 해당 해쉬로 되돌리기 -> 커밋이 이전에 된 상태에서만 가능

git restore . : 현재 작업하고 있는 내용들 초기화 (staging area에 있는 내용)
git clean -fd : 새로 추가된 파일 초기화 (working directory에 있는 내용)

<interactive Rebasing>
서버에 push된 것들은 안하는게 좋음
git rebase -i hash : 원하는 해쉬의 커밋 메세지를 수정할 수 있다.


git 커밋은 한번에 한가지 기능씩만 해야한다. 
근데 만약 두개의 기능을 한번에 넣었는데 아직 push하지 않았다.
그러면 이 커밋을 한가지 기능씩 분리할 수 있다.

먼저 분리할 커밋의 이전 hash로 이동 -> git reset HEAD~1 -> 한가지씩 add, commit 해줌
-> 기능별로 커밋 되었으면 git rebase --continue하면 됨


<fetch>
git fetch : 로컬 HEAD는 기존 로컬 프로젝트를 가리키고 있음


<pull>
git pull을 했을때 같은 파일을 건들여서 충돌이 났을 경우
git mergetool을 이용해서 충돌 부분을 수정해준다.
git add . -> git merge --continue   -> 하지만 이렇게 하면 커밋 히스토리가 더러워진다

git pull --rebase
git mergetool
git rebase --continue 해주면 매우 깔끔하게 히스토리가 작성됨
git push

git blame ?

git bisect 공부해보기
tig

npm ci => npm i 를 하면 git에서 변경되는 부분이 있어 충돌의 위험이 있다. 하지만 npm ci를 해줬을 경우 
	  모듈의 버전을 유지해주면서 모듈을 install해주기 때문에 충돌의 위험이 사라진다.

<Typescript + React>
프로젝트 생성
typescript + react => npx create-react-app 프로젝트명 --template typescript 

기존 프로젝트에 추가
npm install --save typescript @types/node @types/react @types/react-dom @types/jest
