# 보조 웹사이트
[보조 웹사이트(얄코)](https://www.yalco.kr/lectures/git-github/)
[보조 유튜브 영상(얄코)](https://www.youtube.com/watch?v=1I3hMwQU6GU&t=168s)
# 깃이란?

-  VCS(Version Control System) 중 하나
	- 프로그램의 버전 관리를 위한 도구
	- 프로잭트의 **시간**과 **차원**을 관리한다
		- 시간: 여러가지 버젼에 **공통적으로 포함되어 있는 부분**을 한번에 수정할수 있다.
		- 차원:  로컬에서 먼저 코딩을 진행하고(용량에 구애받지 않고), 빠르게 메인 서버에 업로드를 할수 있다

# 기본 커맨드

## 유저 정보 최초설정 
`git config --global user.name "(본인이름)"`

`git config --global user.email "(본인 이메일)"`

- 확인은 "(내용)" 을 제외한 커맨드

## 기본 브랜치 이름 변경
`git config --global init.defaultBranch main`

## 프로젝트 생성 & Git 관리

- 한 프로젝트의 최상위 폴더를 생성하고 그것을 VS Code 로 열면 터미널이 자동으로 그 폴더로 네비게이션된다
	- 따라서 Git 명령어를 VS Code 터미널에 바로 사용할 수 있다
### CLI
`git init`
- Git이 이 프로젝트를 관리하라고 지정
- 숨긴 파일 .git 파일이 생성됨
	- **과거내역, 다른 차원**이 여기에 관리된다
### GUI(SourceTree)
현존하는 레퍼지토리를 추가
- 소스트리에 폴드를 드래그하거나, ` add `

새로운 레퍼지토리 생성
- 소스트리에 폴더를 드래그 하거나, `create`

## Git에게 맡기지 않을 것들

### 파일/폴더를 Git으로부터 배제해야하는 경우
- 포함할 필요가 없는 경우
	- 자동으로 생성 또는 다운로드되는 파일들
		- 빌드 결과물: ( .class)
		- 라이브러리

- 포함하면 안되는 경우
	- 보안상 민감한 정보를 담은 파일

### `.gitignore` 파일을 통 배제할 파일을 지정할 수 있다
- 폴더에 `.gitignore` 파일을 생성후, 배제할 파일 명을 입력하면 그 파일은 배제된다
- `git status`를 입력시 `.gitignore` 이라고 통합되어서 표시된다

### `.gitignore` 형식

[보조 웹사이트 참조]([https://git-scm.com/docs/gitignore](https://git-scm.com/docs/gitignore))

```python
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

## 폴더 현황 체크
`git status`
- 현재 폴더의 상황을 git의 관점에서 보여준다
	- 새로생긴 파일, 삭제된 파일, 변경된 파일, 등
- **Untracked file**: Git의 관리에 들어간 적 없는 파일

`git diff`
- 변경된 사항들을 더 구체적으로 확인할 수 있다


## 변화를 타임캡슐에 넣기(`git add`)
- `git add (파일 이름)`
- `git add .`: 모든 파일을 add하기

## 타임캡슐을 묻기(`git commit`)
- `git commit`
	- 하나의 버젼으로 저장이 된다 
	- `git commit -m "버전 이름"` 으로 빠르게 가능하다
- **SourceTree**에서 작업
	1. 내가 원하는 변경사항을 스테이지(타임캡슐)에 넣기
	2. 왼쪽 위 `commit` 버튼을 누르고 버전 이름 입력후 커밋
- Vi 입력모드

| 작업 | Vi명령어 | 상세 |
| ---- | ---- | ---- |
| 입력 시작 | i | 명령어 입력 모드에서 텍스트 입력모드로 전환 |
| 입력 종료 | `esc` | 텍스트  입력 모드에서 명령어 입력 모드로 전환 |
| 저장없이 종료 | :q |  |
| 저장없이 강제종료 | :q! | 입력한 것이 있을 때 사용 |
| 저장하고 종료 | :wq | 입력한 것이 있을 때 사용 |
| 위로 스크롤 | k | `git log` 등에서 내역이 길때 사용 |
| 아래로 스크롤 | j | `git log` 등에서 내역이 길때 사용 |
- [참조]([마우스 없이 코딩한다구요? | 얄코 (yalco.kr)](https://www.yalco.kr/10_vim/))

## Tip: `add` 와 `commit`을 한번에
`git commit -am "(버전 이름)"`
- 새로 추가된(Untracked) 이 없을 경우에 한정

## `Commit` 히스토리 확인
`git log`
- 과거 버전들을 시간 순으로 보여준다
- **위치한 브랜치**에서의 내역만 가능

`git log --all --decorate --oneline --graph`
- 여러 브랜치의 커밋을 그래프로 표현 해준다
# 과거회귀(과거 버전 불러오기)

- **`.gitignore` 안의 파일들은 영향을 받지 않는다**
### Reset
- 돌아가고자 하는 버전 이후의 버전을 삭제하고 말 그대로 시간을 돌아가듯이 돌아감

1. `git log` 에서 돌아가고자하는 커밋의 해쉬를 복사한다
	 ![[Pasted image 20231226211101.png|400]]
2. `git reset --hard (커밋의 해쉬)` 입력
	- `git reset --hard 3122488c9074c5141db21eb84fcaa95957d75895`

#### **reset** 하기 전 시점으로 돌아가기
- `git reset --hard`
	- 마지막 커밋을 한 직후 상태로 돌아간
#### **SourceTree**에서 작업
- 원하는 커밋 우클릭 후 `reset current branch to this commit` 클릭
- 선택지에서 `Hard`선택

### Revert
- 돌아가고자 하는 버전의 변화를 역으로 수행하는 새로운 버전을 만든다
	- **수정하고자 하는 부분**만 돌릴 수 있다
	- 수정 할 부분 그 이후의 행적은 그대로 유지할 수 있다

1. 돌아갈 커밋의 해쉬를 찾는다
2. `git revert (커밋 해쉬)`
3. `:wq`로 커밋 저장

#### **Revert** 도중의 충돌
 내가 되돌리고자하는 파일만 돌리는 것이기 때문에 그 과정에서 충돌이 생길수도 있다
 - 예를 들어 내가 되돌릴 경우 삭제될 파일이 그 이후에 수정될 예정일 경우, 등
 - 그 경우 컴퓨터가 결정을 하지 못하고 프로그래머가 직접 수정해줘야 한다
	 - `git rm (파일명)` 으로 깃이 관리하는 파일 목록에서 삭제할 수 있다
 - 그 후 `git revert --continue` 입력

#### 커밋하지 않고 **Revert** 하기
`git revert --no-nocommit (커밋 해쉬)`
- 다른 작업들과 함께 커밋하고 싶을때
- 취소 할거면 `git reset --hard`

#### **SourceTree**에서 작업
- `Revert`할 파일 우클릭 후 `reverse commit`

# 차원(Branch) 넘나들기

- 프로젝트를 하나 이상의 모습으로 관리해야할 때
	- Ex) 실 배포용, 테스트서버용, 새로운 시도용
- 여러 작업들이 각각 독립되어 진행될때
	- Ex) 신기능 1, 신기능2, 코드 개선, 긴급수정...
	- **각각의 차원에서 작업한 뒤 확정된 것을 메인 차원에 통합**

## Branch 생성 / 이동 / 삭제

1. `git branch (branch 이름)`
	- 브랜치 생성
2. `git branch`
	-  로컬 브랜치 목록 확인
	- `git branch -a`: 레포지토리의 브랜치까지 확인인
1. `git switch (branch 이름)`
	- ... 브랜치로 이동
2. `git switch -c (branch 이름)`
	- 브랜치 생성과 동시에 이동
3. `git branch -d (branch 이름)`
	 - 브랜치 삭제
4. `git branch -D (branch 이름)`
- 강제삭제: 지워질 브랜치에만 있는 커밋이 있을 경우(다른 브랜치로 가져오지 않은 커밋이 있을 경우)
5. `git branch -m (기존 이름) (새 이름)`
	- 브랜치 이름 바꾸기

## Branch 병합
### **Merge**: 두 브랜치를 **한 커밋**에 이어붙임
![[Pasted image 20240102201708.png||300]]
- 브랜치 **사용내역을 남길 필요**가 있을 때
- `merge`도 하나의 커밋이기 때문에 reset으로 돌릴 수 있다


1. 합쳐질 branch 로 이동
2. `git merge (합칠 branch)`
3. `:wq` 로 저장
4. 불필요한 브랜치 삭제

### **Rebase**: 브랜치를 다른 브랜치에 이어붙임
![[Pasted image 20240102201736.png|300]]
- 한 줄로 **깔끔히 정리된 내역을 유지**하기 원할 때
- 이미 팀원과 공유된 커밋들에 대해서는 사용하지 않는 것이 좋다

1. 합칠 branch 로 이동
	- **`merge` 때와는 반대**
2. `git rebase (합쳐질 branch)`
3. 합쳐질 브랜치로 이동 후 `merge` 커맨드로 가장 최근 브랜치의 시점으로 **fast-forward**
4. 불필요한 브랜치 삭제

### Branch간 충돌
- 파일의 같은 위치에 다른 내용이 입력된 상태

#### Merge 충돌
- **모든 충돌을 하나의 커밋**으로 묶어서 해결

![[Pasted image 20240102205852.png|500]]
- `Accept Current Change`
	- 합쳐질 Branch 채용
- `Accept Incoming Change`
	- 합칠 Branch 채용
- `Accept Both Changes`
	- 둘 다 채용
- `Compare Changes`

- 당장 충돌 해결이 어려울 경우 아래 명령어로 `merge` 중단
	- `git merge --abort`
- 해결 가능시 충돌부분 수정 후 **add & commit**

#### Rebase 충돌
- 합쳐질 브랜치 안에 있는 **모든 커밋에 대하여 충돌을 각각 해결**해야 함

- 당장 충돌 해결이 어려울 경우 아래 명령어로 `rebase` 중단
	- `git rebase --abort`
- 해결 가능시
	-  수정 후 `git add .`
	- `git rebase --continue`
	- 모든 충돌 해결까지 반복

# GitHub
## Repository 기본 설정들

한 프로젝트에 대한 원격 저장소
- `public`: 모두에게 보일수 있는 프로젝트(오픈소스)
- `private`: 허용된 인원만 볼 수 있는 프로젝트

협업 팀원 추가
-  Repository의 `setting` -> `collaborators`
- `add people`

Repository와 VS Code 연동하기
- 새로운 Repository 생성
- 새 프로젝트 생성
	- 위 옵션 복붙
- 기존의 프로젝트 연동
	- 아래 옵션 복붙
- 자격증명관리자 세팅(토큰)이 제대로 되어있다면 끝

`git remote add origin (레포지토리 주소)`
- 새로운 원격 저장소를 추가한다
- `origin`: 원격 저장소의 디폴트이름
	- 일반적으로 많이 사용됨

`git branch -M main`
- 레포지토리의 메인 브랜치 이름을 `main`으로 함

`git push -u origin main`
- `-u origin main`: 푸쉬경로를 `origin main`으로 설정함
- 한 프로젝트에 여러개의 레포지토리를 사용할 수 있기 때문

## 관련 커맨드

`git remote`
- 프로젝트와 연결된 레포지토리를 확인 할 수 있다
- `git remote -v`: 레포지토리의 자세한 설명을 볼 수 있다

`git remote remove (레포지토리의 이름 ex) origin)`
- 레포지토리와의 연결 끊기(레포지토리는 지워지지 않음)

### GitHub에서 프로젝트 다운받기

![[Pasted image 20240107013203.png|300]]

파일만 다운받기
- `Download Zip`
- `.git`파일은 제외(커밋관련 내용제외)

Git관리내역까지 복사
1. 다운받을 폴더에서 우클릭 후 `Open Git Bash here`클릭
![[Pasted image 20240107013708.png|250]]
2. GitHub에서 `Clone`목록중 `HTTPS`링크 복사
3. `Bash` 에서 `git clone (HTTPS링크)` 입력
	- 토큰관련 이슈가 없다면 끝

### Push & Pull
`git push`
- 로컬 내용을 GitHub에 업로드

`git pull`
- GitHub내용을 로컬에 다운로드

**`push`하기 전에 `pull`해야하는 경우**
- GitHub에서는 push하기 전에 로컬을 레포지토리와 같은 버젼으로 최신화를 해줘야 한다
- `git pull --no-rebase`: `merge` 방식
- `git pull --rebase`: rebase방식
- 그 후 `push`

`Push` & `Pull` 동안의 충돌
- 브랜치간 충돌 해결방식과 동일

강제 `Push`
- 레포지토리에 문제가 생겨서 강제로 로컬파일을 덮어씌워야 할 때
- 레포지토리를 강제로 로컬과 동기화시킴
- `git push --force`

## 레포지토리의 브랜치

로컬에서 새로운 브랜치를 생성하고 `push`를 할 경우, 레포지토리의 어느 브랜치에 `push`할지 설정되어 있지 않기 때문에 오류가 발생함

`git push -u origin(레포지토리 이름) (새로운 브랜치 이름)`
- 레포지토리의 브랜치를 생성후 경로를 설정

레포지토리의 브랜치 다운로드
1. `git fetch`: 원격에서의 변화를 로컬에서도 확인할 수 있음
2. `git switch -t (레포지토리 이름)/(브랜치 이름)` 입력
	- `-t`: 원격의 브랜치를 로컬에 복사후 연결하겠다

레포지토리의 브랜치 삭제
- `git push (레포지토리 이름) --delete (레포지토리의 브랜치 이름)`
