# Appendix

---

## Git 용어

---

git 용어에 대한 설명을 간단하게 적어 놓았습니다.

모든 코드에서  중괄호 `{}` 는 제외하고 입력하시면 됩니다.

| index | item | index | item |
| --- | --- | --- | --- |
| 1 | [add](https://github.com/fusillading/test_repo/blob/main/README.md#add) | 12 | [log](https://github.com/fusillading/test_repo/blob/main/README.md#log) |
| 2 | [branch](https://github.com/fusillading/test_repo/blob/main/README.md#branch) | 13 | [merge](https://github.com/fusillading/test_repo/blob/main/README.md#merge) |
| 3 | [checkout](https://github.com/fusillading/test_repo/blob/main/README.md#checkout) | 14 | [origin](https://github.com/fusillading/test_repo/blob/main/README.md#origin) |
| 4 | [clone](https://github.com/fusillading/test_repo/blob/main/README.md#clone) | 15 | [pull](https://github.com/fusillading/test_repo/blob/main/README.md#pull) |
| 5 | [commit](https://github.com/fusillading/test_repo/blob/main/README.md#commit) | 16 | [pull request](https://github.com/fusillading/test_repo/blob/main/README.md#pull-request) |
| 6 | [config](https://github.com/fusillading/test_repo/blob/main/README.md#config) | 17 | [rebase](https://github.com/fusillading/test_repo/blob/main/README.md#rebase) |
| 7 | [diff](https://github.com/fusillading/test_repo/blob/main/README.md#diff) | 18 | [remote](https://github.com/fusillading/test_repo/blob/main/README.md#remote) |
| 8 | [git](https://github.com/fusillading/test_repo/blob/main/README.md#git) | 19 | [rm](https://github.com/fusillading/test_repo/blob/main/README.md#rm) |
| 9 | [github](https://github.com/fusillading/test_repo/blob/main/README.md#github) | 20 | [reset](https://github.com/fusillading/test_repo/blob/main/README.md#reset) |
| 10 | [init](https://github.com/fusillading/test_repo/blob/main/README.md#init) | 21 | [repository](https://github.com/fusillading/test_repo/blob/main/README.md#repository) |
| 11 | [issues](https://github.com/fusillading/test_repo/blob/main/README.md#issues) | 22 | [status](https://github.com/fusillading/test_repo/blob/main/README.md#status) |













### add

---

```bash
git add {파일이름}
단일 파일 추가
git add .
모든 파일 추가
```

add라는 뜻 그대로 더한다는 뜻입니다. 

작업 디렉토리(working directory) 상의 변경 내용을 스테이징 영역(staging area)에 추가합니다.

### branch

---

```bash
git branch {branch 이름}
branch를 생성
```

나뭇가지 혹은 갈라지다라는 뜻을 가지고 있는 단어입니다.

git은 하나의 프로젝트를 여러 갈래로 나누어서 작업할 수 있도록 하는데, 이 때의 갈래를 branch라고 합니다.

### checkout

---

```bash
git checkout {branch 이름}
작업하는 branch를 변경
git checkout -b {branch 이름}
branch를 생성하고 해당 branch로 전환
```

작업하는 branch를 변경할 수 있도록 하는 명령어입니다.

### clone

---

```bash
git clone {원격 저장소 주소} {복제 경로}
원격 저장소의 내용을 복제 경로로 복제
(복제 경로는 생략 가능)
```

clone은 복제하다라는 뜻을 가지고 있습니다.

말 그대로 원격 저장소의 내용을 원하는 경로로 복제할 수 있습니다.

### commit

---

```bash
git commit -m "commit 메세지 내용"
메세지 내용과 함께 commit
```

commit은 새기다, 기록하다라는 뜻을 가지고 있습니다.

파일 및 폴더의 추가/변경 사항을 저장소에 기록합니다.

### config

---

```bash
git config --{범위} {이름} {값}
원하는 범위에서 설정을 변경
git config {이름}
현재 설정 읽기
```

config는 구성이라는 뜻을 가지고 있습니다.

기본적인 설정을 변경하고 읽어올 수 있습니다.

### diff

---

```bash
git diff
```

diff는 느끼셨다시피 difference에서 유래한 명령어입니다.

스테이지에 있는 파일과 저장소에 있는 최신 커밋을 비교해서 보여줍니다

### git

---

git은 영국의 속어로 ‘고집 센 사람’, ‘항상 자기 자신이 옳다고 생각하며 따지기 좋아하는 사람’의 뜻을 가지고 있습니다.

git은 버전관리 시스템으로서 협업에 있어서 많은 장점을 제공합니다.

### github

---

hub는 ‘중심지’, ‘중추’의 뜻을 가지고 있습니다. 택배가 모이는 옥천도 옥천hub라는 말로 표현하는 것을 떠올리시면 좋습니다.

github는 git을 호스팅하는 일종의 클라우드 서비스입니다. 서로의 코드를 공유할 수 있습니다.

### init

---

```bash
git init
git을 시작
```

init은 initialize(initialise)의 약자입니다. initialize는 초기 내용을 설정하다라는 의미를 가지고 있습니다.

마찬가지로 init 명령어는 해당 디렉토리에서 git을 시작하기 위해 사용됩니다.

### issues

---

issues 탭에서는 repository들에서 올라오는 질문이나 의견들을 볼 수 있습니다.

### log

---

```bash
git log
```

log는 ‘기록’이라는 뜻을 가진 단어입니다.

commit 기록을 볼 수 있습니다. commit 기록에는 commit 고유값,  commit한 사람, 날짜/시간, commit 메세지가 포함됩니다.

### merge

---

```bash
git merge {branch 이름}
해당 branch를 main branch에 병합
```

merge는 ‘병합’이라는 뜻을 가진 단어입니다.

원하는 branch를 main branch에 병합할 때 사용합니다.

### origin

---

origin은 ‘기원’, ‘근원’을 뜻하는 단어입니다.

origin은 원격 저장소의 주소의 별명을 의미합니다.

(clone 기능을 사용하여 프로젝트를 가져올 경우 자동으로 origin으로 등록됩니다.)

### pull

---

```bash
git pull origin {branch 이름}
기본적으로 생성되는 branch의 이름은 main
```

pull은 ‘당기다’라는 의미를 가지고 있습니다.

원격 저장소에서 변경 사항을 현재 디렉토리로 가져옵니다.

### pull request

---

pull request는 자신이 코드를 수정했으니 협업자에게 branch를 가져가 검토 후 병합해달라고 요청하는 것입니다.

### rebase

---

```bash
git rebase {branch 이름}
기본적으로 생성되는 branch의 이름은 main
```

rebase는 ‘새로운 기준을 설정한다’라는 의미를 가지고 있습니다.

한 브랜치에서 변경된 사항을 다른 브랜치에 적용할 수 있습니다.

(이 기능은 merge 대신에 사용할 수 있지만 추천되지 않습니다)

### remote

---

```bash
git remote add origin {원격 저장소 주소}
원격 저장소를 git에 등록
```

remote는 ‘원격의’라는 뜻을 가지고 있습니다.

원격 저장소를 git에 등록합니다.

### rm

---

```bash
git rm {파일명}
git commit -m "{파일명} 삭제"
로컬 디렉토리와 git 저장소에서 모두 삭제

git rm --cached {파일명}
git commit -m "{파일명} 삭제"
로컬 디렉토리에서는 삭제하지 않지만, git 저장소에서는 삭제
```

rm은  remove의 약자입니다. 

파일을 삭제합니다.

rm을 한 후에는 꼭 commit을 해주어야 적용됩니다.

### reset

---

```bash
git reset {option} {돌아가고 싶은 commit의  고유값}
돌아가고 싶은 commit

git reset HEAD^
최신 commit으로 되돌리기

git reset HEAD~2
최신 commit에서 2개 전 commit으로 되돌리기
```

reset은 돌아가고 싶은 commit으로 돌아가는 기능입니다.

돌아가고 싶은 commit의 고유값은 log 명령어를 통해서 얻을 수 있습니다.

### repository

---

repository는 우리말로 저장소 입니다. 개발에 대한 정보(폴더, 파일 등)를 저장하는 곳입니다. repository는 장소에 따라서 개인 컴퓨터에 저장되어 있는 것을 local repository, github과 같은 클라우드에 저장되어 있는 것을 remote repository라고 합니다.

### status

---

```bash
git status
```

status는 상태라는 뜻을 가지고 있습니다.

파일들의 상태를 확인할 수 있습니다. 주로 변경사항을 확인할 때 사용합니다.
