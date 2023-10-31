# [실습] Let's git it started 시작하기


<aside>
🙌 <b>[이론편](https://github.com/JNU-econovation/Let-s-git-it-started/blob/docs/guide/guide.md)</b> 잘 확인하고 오셨나요?

이번에는 앞에서 배운 내용을 바탕으로 직접 행사를 참여하는 실습을 진행하려고 합니다. 상세한 설명을 확인하고 싶으신 분들은 [이론편](https://github.com/JNU-econovation/Let-s-git-it-started/blob/docs/guide/guide.md)을 참고해주세요! 

</aside>

Let's git it started행사는 Git 저장소를 생성 및 초기 설정하는 [1)Git init하기](#1--git-init), 원본 저장소를 내 계정으로 복사하는 [2) fork 하기](#2--fork), 자신의 local에 원격 저장소를 등록하고 소스를 가져오는 [3) remote, pull 하기](#3--remote-pull), 자신을 소개하는 글을 작성하여 [4) add, commit, push하기](#4--add-commit-push), 나의 원격 저장소에서 원본 원격 저장소로 [5) Pull Request 하기](#5--pull-request), 서로의 소개글을 읽으면서 궁금하거나 공감가는 내용은 [6) Review 기능을 이용해 소통하기](#6--review), 6명 이상의 리뷰어로부터 승인 받을 시 [7) Merge 받기](#7--merge)의 7단계로 이루어집니다. 

1. [git init](#1--git-init)
2. [fork](#2--fork)
3. [remote, pull](#3--remote-pull)
4. [add, commit, push](#4--add-commit-push)
5. [Pull Request](#5--pull-request)
6. [Review](#6--review)
7. [Merge](#7--merge)





# 1 ) git init
git init은 새로운 Git 저장소를 생성할 때 사용하는 명령어입니다. Let-s-git-it-started 실습을 위한 로컬 저장소를 생성해봅시다. 

1. [작업할 폴더로 이동](#step1-작업할-폴더로-이동)
2. [Git 저장소 생성 및 최초 설정](#step2-git-저장소-생성-및-최초-설정)



## Step1. 작업할 폴더 생성 및 이동
> 실습을 진행할 폴더를 생성하고, 해당 폴더를 작업 폴더로 선택합니다.
>

### 1. **cd {경로}**

git bash(Window) 혹은 terminal(MacOS)에서 작업할 폴더로 이동합니다.
```bash
$ cd desktop
```
위와 같이 작성한 경우, 현재 작업 중인 폴더의 하위 폴더인 `desktop`으로 이동합니다.

### 2. **mkdir {폴더명}**
새로운 폴더를 생성합니다.
```bash
$ mkdir practice
```
위와 같이 작성했을 때, 현재 작업 중인 폴더의 하위에 `practice`라는 폴더를 생성합니다.

### 3. **ls**
현재 위치 혹은 특정 경로의 내용을 리스트로 출력합니다.
```bash
$ ls
```
현재 작업 중인 폴더에 있는 내용을 출력합니다.

저는 홈 폴더의 하위에 있는 `desktop`이라는 폴더로 이동 후 `practice`라는 폴더를 생성한 뒤, 해당 폴더로 이동해보도록 하겠습니다. 홈 폴더는 `~` 와 같이 표시합니다.

<center>
<img src = "https://github.com/JNU-econovation/Let-s-git-it-started/assets/114472483/76451902-6e2a-4919-a13e-686d376324b9" width = "700">
</center>



## Step2. Git 저장소 생성 및 최초 설정
> git 저장소를 생성 후 최초 설정을 하는 과정입니다.
> 

### 1. **git init**
    
`cd`, `mkdir`, `ls` 등의 명령어를 활용하여 작업을 진행할 디렉토리를 자유롭게 생성 및 선택합니다. 실습을 위해 생성한 디렉토리에서 명령을 실행합니다. 


- 디렉토리명과 원격저장소명은 달라도 괜찮습니다.

```bash
$ git init
```

이 폴더에서 git을 실행할거야! 라는 의미입니다.

저는 실습을 위해 생성한 `practice`라는 폴더에서 `git init` 명령어를 실행해보도록 하겠습니다.

<center>
<img src = "https://github.com/JNU-econovation/Let-s-git-it-started/assets/114472483/20cf6057-9e0f-4c5c-87cd-8bf42901bb19" width = "700">
</center>

`git init` 명령을 실행했을 때, 이전과는 달리 경로의 오른쪽에 `(master)`혹은 `(main)`이라는 푸른색 글씨가 나타난 것이 보입니다. 이제 `practice` 폴더의 내용은 버전 관리가 가능하게 되었습니다.

- `ls -al`을 통해 숨김 디렉토리를 확인하면 **.git 디렉토리**가 생성된 것을 확인할 수 있습니다.

### 2. **git config --global**

커밋을 할 때 사용할 이름과 이메일을 설정합니다. 커밋이 무엇인지는 [4) add, commit, push하기](#4--add-commit-push)에서 확인할 수 있습니다. 이 과정은 이전에 git을 사용해본 적이 있다면 생략해도 좋습니다. 환경 설정은 한 컴퓨터에서 한 번만 해도 괜찮기 때문입니다. 물론 정보 수정은 얼마든지 가능합니다.

```bash
$ git config --global user.name "{Your name}"
$ git config --global user.email "{Your email}"
```

### 3. **git config --list**

아래의 명령어를 통해 이름과 이메일이 제대로 설정되었는지 확인할 수 있습니다.

```bash
$ git config --list
```





# 2 ) Fork

Fork 기능은 다른 계정의 원격 저장소에 있는 내용을 내 계정의 원격 저장소로 가지고 올 때 사용합니다. 이 실습에서는 [JNU-econovation의 Let-s-git-it-started](https://github.com/JNU-econovation/Let-s-git-it-started) 저장소를 내 계정의 원격 저장소로 가지고 오기 위해 사용합니다.

- [다른 원격 저장소를 내 원격 저장소로 복제(Fork)](#step1-다른-원격-저장소를-내-원격-저장소로-복제fork)
<center>
<img src = "https://github.com/JNU-econovation/Let-s-git-it-started/assets/114472483/ced63586-f4e5-46af-8f9c-a990ad1a67af" width = "700">
</center>



## Step1. 다른 원격 저장소를 내 원격 저장소로 복제(Fork)
> Github에서 다른 계정의 원격 저장소를 Fork해옵니다.
### 1. **복사하고자 하는 원격 저장소에서 Fork버튼 누르기**

복사하고자 하는 원격 저장소에 들어가 Fork 버튼을 클릭합니다. 이번 실습에서 Fork를 진행할 레포지토리는 [JNU-econovation의 Let-s-git-it-started](https://github.com/JNU-econovation/Let-s-git-it-started)입니다.

<center>
<img src = "https://github.com/JNU-econovation/Let-s-git-it-started/assets/114472483/3ba423cc-9f70-4999-a1b2-b286a341acee" width = "700">
</center>

### 2. **Create a new fork 창에서 설정 후 Create fork버튼 누르기**

Fork 버튼을 누르면 나타나는 Create a new fork 창에서 Create fork 버튼을 클릭합니다. 이번 실습에서 기본값 이외에 추가적으로 설정해야 하는 값은 없습니다.

<center>
<img src = "https://github.com/JNU-econovation/Let-s-git-it-started/assets/114472483/3b0bdf03-49ba-4861-b15d-9f8869fe6fa3" width = "700">
</center>

### 3. **복사한 저장소가 내 계정으로 잘 복사되었는지 확인하기**

Fork 과정을 완료하였다면, 내 계정에 Let-s-git-it-started 레포지토리가 잘 복사되었는지 확인합니다. 

<center>
<img src = "https://github.com/JNU-econovation/Let-s-git-it-started/assets/114472483/a30f7230-3f28-4de2-b74a-94c02ecb885c" width = "700">
</center>





# 3 ) remote, pull
remote 명령어를 통해 로컬 저장소(내 컴퓨터)와 원격 저장소(깃허브 저장소)를 연결할 수 있으며, pull 명령어를 통해 원격 저장소에 저장 되어있는 내용을 로컬 저장소로 가져올 수 있습니다. 에코노베이션의 Let-s-git-it-started 저장소와 내 로컬 저장소를 먼저 연결한 뒤, Fork 해온 Let-s-git-it-started 저장소와 내 로컬 저장소도 연결해봅시다. 그리고 원격 저장소에서 소스 코드를 가져와봅시다.

1. [개인 로컬(local) 저장소와 원본 원격(remote) 저장소 연결 - JNU-econovation / Let-s-git-it-started와 연결](#step1-개인-로컬local-저장소와-원격remote-저장소-연결---jnu-econovation--let-s-git-it-started와-연결)
2. [개인 로컬(local) 저장소와 원격(remote) 저장소 연결 - fork 해온 Let-s-git-it-started와 연결](#step2-개인-로컬local-저장소와-원격remote-저장소-연결---fork-해온-let-s-git-it-started와-연결)
3. [원격 저장소에 저장되어있는 내용을 가져오기(pull)](#step3-원격-저장소에-저장되어있는-내용을-가져오기pull)

<center>
<img src = "https://github.com/JNU-econovation/Let-s-git-it-started/assets/114472483/d1a97943-e260-460b-82d8-5220ff14193b" width = "700">
</center>



## Step1. 개인 로컬(local) 저장소와 원격(remote) 저장소 연결 - JNU-econovation / Let-s-git-it-started와 연결
> 로컬(local) 저장소와 [JNU-econovation / Let-s-git-it-started](https://github.com/JNU-econovation/Let-s-git-it-started) 저장소를 연결하는 과정입니다.
> 

### 1. **git remote add** 

[JNU-econovation / Let-s-git-it-started](https://github.com/JNU-econovation/Let-s-git-it-started) 저장소를 local git에 등록합니다. 


```bash
$ git remote add upstream https://github.com/JNU-econovation/Let-s-git-it-started
```

[JNU-econovation / Let-s-git-it-started](https://github.com/JNU-econovation/Let-s-git-it-started) 저장소를 `upstream`이라는 이름으로 local git에 등록하는 과정입니다. `upstream`은 등록할 긴 **원격 저장소 주소를 대체할 별명**인데요. 일반적으로 fork 해온 복제 원격 저장소에는 `origin`이라는 명칭을, fork를 시도한 원본 원격 저장소에는 `upstream`이라는 명칭을 주로 사용합니다. 이에 따라 우리도 fork 해온 Let-s-git-it-started 저장소는 `origin`이라는 명칭으로 로컬 저장소와 연결하고, [JNU-econovation / Let-s-git-it-started](https://github.com/JNU-econovation/Let-s-git-it-started) 저장소는 `upstream`이라는 명칭으로 로컬 저장소를 연결할 것입니다. 그렇다면 이제 본격적으로 원격 저장소와 로컬 저장소를 연결해봅시다.

[JNU-econovation / Let-s-git-it-started](https://github.com/JNU-econovation/Let-s-git-it-started) 저장소로 들어가 Code 버튼을 눌러 저장소의 주소를 복사해올 수 있습니다. 아래의 그림을 참고해주세요.

<center>
<img src = "https://github.com/JNU-econovation/Let-s-git-it-started/assets/114472483/e30f8b56-ff01-4500-9ed9-7a36c99db265" width = "700">
</center>

### 2. **git remote -v**

현재의 로컬 저장소와 연결된 원격 저장소들의 정보를 확인합니다.

```bash
$ git remote -v
```
[JNU-econovation / Let-s-git-it-started](https://github.com/JNU-econovation/Let-s-git-it-started) 저장소가 `upstream`이라는 이름으로 등록되었는지 확인합시다.


실제 git bash를 통해 실습한 화면은 다음과 같습니다.
<center>
<img src = "https://github.com/JNU-econovation/Let-s-git-it-started/assets/114472483/4407cbb2-c39d-44e6-9538-a989e3560b8a" width = "700">
</center>



## Step2. 개인 로컬(local) 저장소와 원격(remote) 저장소 연결 - fork 해온 Let-s-git-it-started와 연결


### 1. **git remote add** 

fork해온 Let-s-git-it-started 저장소를 local git에 등록합니다. 


```bash
$ git remote add origin {fork해온 원격 저장소의 주소}
```

fork해온 원격 저장소를 `origin`이라는 이름으로 local git에 등록합니다. 

fork해온 원격 저장소로 들어가 Code 버튼을 눌러 저장소의 주소를 복사해올 수 있습니다. 아래의 그림을 참고해주세요.

<center>
<img src = "https://github.com/JNU-econovation/Let-s-git-it-started/assets/114472483/3f602203-94c2-41d5-8c02-7a6a48fb6f3f" width = "700">
</center>

### 2. **git remote -v**

현재의 로컬 저장소와 연결된 원격 저장소들의 정보를 확인합니다.

```bash
$ git remote -v
```
fork 해온 원격 저장소의 주소가 `origin`이라는 이름으로 등록되었는지 확인합시다.


실제 git bash를 통해 실습한 화면은 다음과 같습니다.
<center>
<img src = "https://github.com/JNU-econovation/Let-s-git-it-started/assets/114472483/5b565271-4111-448c-82cd-d1944f695157" width = "700">
</center>



## Step3. 원격 저장소에 저장되어있는 내용을 가져오기(pull)
> 원격 저장소에서 로컬 저장소로 소스를 가져옵니다.
>

<center>
<img src = "https://github.com/JNU-econovation/Let-s-git-it-started/assets/114472483/ad006841-f018-4a91-9a2a-6c6bbe812be3" width = "700">
</center>

### git pull origin main

등록한 원격 저장소에 담긴 내역을 local에 가져옵니다. 

```bash
$ git pull upstream 2023-2
```

등록된 원격 저장소 주소(`upstream`이 되겠죠?)의 `2023-2` branch에 담긴 내용들을 가져오겠다 라는 의미입니다. 작업하고 있는 local 저장소를 최신 상태로 업데이트하는 과정이기 때문에 협업에서 중요한 과정입니다.

실습 화면을 확인해봅시다.

<center>
<img src = "https://github.com/JNU-econovation/Let-s-git-it-started/assets/114472483/8d6ef681-bb4f-493f-b72c-7fee970dc0ba" width = "700">
</center>


- `ls` 명령어를 실행했을 때, 원격 저장소의 내용들이 불러와진 것을 확인할 수 있습니다.
    
>    <aside>
>    🔎 <b>git clone</b>
>
>    `git clone {GitHub 원격 저장소 주소}` 사용 시 GitHub 원격 저장소 주소의 저장소가 복제됩니다.  
>     Git 저장소를 관리하는 **.git** 디렉토리와 GitHub 원격 저장소 데이터가 모두 담겨 있음을 확인할 수 있습니다.
>   </aside>





# 4 ) add, commit, push
로컬 저장소에서 파일 및 폴더의 변경 사항을 관리하는 명령어가 바로 add와 commit입니다. 또한 지금까지 로컬에서 작업한 내용은 push를 통해 원격 저장소에 업로드할 수 있습니다. 실습을 통해서 작업 폴더의 변경 사항을 직접 관리해봅시다.

1. [준비해 온 자기소개로 글 수정하기](#step1-준비해-온-자기소개로-글-수정하기)
2. [작업 내용을 staging 영역으로 이동하기(add)](#step2-작업-내용을-staging영역으로-이동하기add)
3. [로컬 저장소에 변경 사항 저장하기(commit)](#step3-로컬-저장소에-변경-사항-저장하기commit)
4. [원격 저장소에 변경 사항 반영하기(push)](#step4-원격-저장소에-변경-사항-반영하기push)

<center>
<img src = "https://github.com/JNU-econovation/Let-s-git-it-started/assets/114472483/26ba2deb-c532-4be0-bc0c-22ff2c2d9c8b" width = "700">
</center>



## Step1. 준비해 온 자기소개로 글 수정하기

### 1. **cp**
2023-2 폴더에 있는 profile.md 파일을 복제합니다.
- profile.md는 **절대** 지우지 마세요❗️

```bash
$ cp profile.md {내 깃허브 id}.md
```
`cp` 명령어는 파일이나 폴더를 복사할 때 사용하는 명령어입니다. 위와 같이 입력하면 현재 작업 폴더에 있는 `profile.md`` 파일이 현 위치에 `{내 깃허브 id}.md` 파일로 복사됩니다.

<center>
<img src = "https://github.com/JNU-econovation/Let-s-git-it-started/assets/114472483/ba9cd3a5-cbd6-44a3-af21-8adf82a3b11f" width = "700">
</center>

<figcaption align = "center">
<b>그림6</b> 파일을 복제하여 생성한 모습
</figcaption>
<br></br>

### 2. 복제하여 생성된 파일에서 자유롭게 자신을 소개하는 글을 작성합니다. 
- 자유롭게 양식을 수정하셔도 괜찮습니다 :)
    
>   <aside>
>    ✋ <b>잠깐만~ `.md`로 끝나는 것은 무엇인가요?</b>
> <br></br>

    
>    `.md`로 끝나는 확장자는 Markdown 문법이 적용된 파일임을 의미하는데요.
>
>    Markdown 문법은 쉽고 간단한 문법으로 다양한 플랫폼과 프로그램에서 활용되는 글을 작성할 때 사용하는 문법입니다.
>
>    Markdown 문서를 작업할 때 사용하는 에디터로는 [typora](https://typora.io/), [visual studio](https://code.visualstudio.com/) 등이 있습니다. 문법이 익숙치 않은 분들은 [MarkDown 사용법 총정리 블로그](https://heropy.blog/2017/09/30/markdown/) 글을 참고하여 작업해주세요!  
>
>    </aside>



## Step2. 작업 내용을 staging영역으로 이동하기(add)

### **git add** 

자신을 소개하는 글을 작성하셨나요? 

이제 여러분의 local 저장소 변경사항(글 작성)을 Github에 반영할 차례입니다. 

```bash
$ git add {파일명}
```

저는 `econo.md` 파일을 스테이징 하기 위해서 `git add econo.md` 와 같이 명령어를 입력하였습니다. add 명령 후 `git status` 를 통해 저장소의 상태도 확인해주었습니다. 방금 생성한 `econo.md` 파일이 제대로 추가되었네요! 

<center>
<img src = "https://github.com/JNU-econovation/Let-s-git-it-started/assets/114472483/462ae8f2-bd7b-4163-96c8-7e0138db950f" width = "700">
</center>



## Step3. 로컬 저장소에 변경 사항 저장하기(commit)

### **git commit** 

    
변경 사항을 기록하는 것을 커밋이라고 합니다. 

이때 어떤 변경 사항이 있는지 설명하는 것을 커밋 메시지라고 하는데요. 커밋은 이력을 남기는 중요한 작업이므로 커밋 메시지는 필수입니다. 

- 원활한 협업을 위해서 올바른 커밋 메시지를 작성하는 것이 중요합니다. 함께 협업하는 동료와 함께 커밋 메시지 컨벤션을 만들어 협업해보세요!

```bash
$ git commit -m "{남길 commit message}"
```

<center>
<img src = "https://github.com/JNU-econovation/Let-s-git-it-started/assets/114472483/32da437b-4b50-4036-8ee4-1e493915a452" width = "700">
</center>


저는 "docs: add econo.md" 라는 커밋 메시지와 함께 변경 사항을 기록했습니다. 



## Step4. 원격 저장소에 변경 사항 반영하기(push)
> 로컬(local) 저장소에서 자기소개를 작성한 후, 원격 저장소에 반영(push)하는 과정입니다.
>

<center>
<img src = "https://github.com/JNU-econovation/Let-s-git-it-started/assets/114472483/99e759e2-3dcc-454b-a890-c3695382fcc7" width = "700">
</center>

### **git branch**
- 현재 작업 중인 branch명이 **`main`이 아닌** 경우 진행합니다❗️

깃허브에서는 main으로 브랜치가 설정되어 있기 때문에, 터미널에 반영되어있지 않다면 바꿔줍니다.

<center>
<img src = "https://github.com/JNU-econovation/Let-s-git-it-started/assets/114472483/4e93799e-34d0-4fba-aded-9e7a3e776125" width = "700">
</center>

### **git push**
이제 업로드할 준비는 다 완료되었습니다. 지금까지는  local에서 변경 이력을 남긴 것이고 이제 이것을 원격(remote) 저장소에 전송합니다.

```bash
$ git push origin {branch명}
```

`origin`은 원격 저장소(remote)의 주소를 의미하는데요. `origin`이라는 원격저장소에 현재 작업 중인 branch에서 남긴 코드 변경 이력을 올리는 과정입니다.

예를 들어, 저는 main이라는 branch에서 자기소개글을 작성했고 이 변동 사항을 origin에 올리기 때문에 명령어는 다음과 같습니다.

```bash
$ git push origin main
```

명령어 실행 결과, fork해온 원격 저장소에서 main이라는 브랜치에 local에서 작업한 내용이 업로드 되었음을 확인할 수 있습니다.

<center>
<img src = "https://github.com/JNU-econovation/Let-s-git-it-started/assets/114472483/bb85ee27-1dfc-497e-b0ef-2025eea1a984" width = "700">
</center>

<center>
<img src = "https://github.com/JNU-econovation/Let-s-git-it-started/assets/114472483/e3fb1130-d3b6-4b28-93ab-69b3c5b2db7e" width = "700">
</center>




# 5 ) Pull Request

Pull Request(PR)은 자신이 변경한 내용을 동료에게 전달하는 과정입니다. 이 실습에서는 자신의 자기소개를 동료들에게 공유하기 위해 Pull Request를 만드는 거죠!

- [Pull Request 생성](#step1-pull-request-생성)
    
<center>
<img src = "https://github.com/JNU-econovation/Let-s-git-it-started/assets/114472483/59e9cba7-5d1a-4171-ba10-3dabcd67b33a" width = "700">
</center>

## Step1. Pull Request 생성

> 자신이 반영한 내역(자기소개 작성 후 추가)을 공유하는 과정입니다.
> 
> - 내가 개발한 코드 변경 사항을 fork를 시도했던 원본 저장소에 반영하고 싶을 때 기존 프로젝트 소유자에게 요청하는 작업을 ***Pull Request한다*** 라고 합니다.

이제 모든 준비가 다 되었습니다. 변경한 내용을 전달해보아요!

### 1. Fork 해온 Let-s-git-it-started 저장소에서 에서 Pull requests 탭으로 이동한 후, [New pull request] 버튼을 클릭합니다.   

<center>
<img src = "https://github.com/JNU-econovation/Let-s-git-it-started/assets/114472483/b369568c-a5b1-4c63-b0a4-17de16e63eef" width = "700">
</center>

### 2. Pull Request의 방향을 맞춰준 후 [Create Pull Request] 버튼을 클릭합니다.

- "*JNU-econovation / Let-s-git-it-started 의 {해당 학기 브랜치}*" 로 "*{내 깃허브 아이디} / Let-s-git-it-started의 main브랜치*"의 Pull Request를 요청하면 됩니다.

<center>
<img src = "https://github.com/JNU-econovation/Let-s-git-it-started/assets/114472483/f667e653-4602-4780-9a1c-5ea18b61b3f8" width = "700">
</center>
    
### 3. Pull Request를 생성합니다.

1. Pull request 제목, 내용을 작성합니다. (규칙에 맞게 작성해주세요!)
    - 제목: 자신의 이름(Github 아이디) 자기소개

        ex. 에코노(econo) 자기소개

    - 내용: 간단한 한줄 소개 등 자유롭게 구성

        ex. 안녕하세요! 에코노베이션 25기 에코노입니다.

2. PR에 대한 라벨을 지정합니다. 
    - `자기소개` 라벨과 `자신의 기수`를 나타내는 라벨을 지정해주세요.
3. 마지막으로 [Create pull request] 버튼을 클릭합니다. 

**❗️위 조건을 모두 만족하신 분들에 한해 approve해드리니! 꼭 확인해주세요** 

<center>
<img src = "https://github.com/JNU-econovation/Let-s-git-it-started/assets/114472483/4f720252-9bd8-4780-966c-5439250cedf0" width = "900">
</center>



    

# 6 ) Review

Pull Request(PR)을 통해 자신이 변경한 내용을 동료에게 전달했으면, 동료는 잘 작업이 되었는지 검토 과정이 필요한데요. 

예를 들어, 저희 TF팀이 함께 이 github자료를 만든다고 해봅시다. 제가 실습 부분을 작성했고 작성한 내용을 도연님, 건형님, 배경님께 전달하기 위해 Pull Request(PR)를 작성하고 이 분들은 제가 작성한 내용이 github 자료에 들어가도 괜찮을지, 잘못된 부분은 없는지 아마 검토하실 것입니다.

우리는 github이 제공하는 리뷰 기능을 이용해 자기소개를 읽으면서 궁금한 점은 질문하고 공감하면서 서로 알아가는 시간을 갖는 것을 목표로 합니다. 



### 1. 리뷰할 사람의 Pull Request를 클릭합니다. 
    
<center>
<img src = "https://user-images.githubusercontent.com/79842129/229303418-917b8ff8-3f6a-4a0b-83fe-8729ea50470f.png" width = "700">
</center>
    

### 2. 해당 Pull Request에서 Files changed 탭을 클릭합니다. 
    
<center>
<img src = "https://user-images.githubusercontent.com/79842129/229303417-252baaa7-a644-4218-981c-42de68ee9656.png" width = "700">
</center>
    

### 3. 공감가는 내용이 있는 줄의 [+] 버튼을 클릭하여 자유롭게 의견을 작성한 후 [Start a review] 버튼을 클릭합니다. 
    
<center>
<img src = "https://user-images.githubusercontent.com/79842129/229303416-36f6a614-1c2e-44c9-aa8a-a64f3dfd6c2e.png" width = "700">
</center>


### 4. 모든 Review를 작성하셨다면 [Review changes] 버튼을 클릭하고 설정한 후 Review를 제출합니다.

<center>
<img src = "https://user-images.githubusercontent.com/79842129/229303787-5c4dd4c1-6b4f-4810-ace0-5a14480c6d96.png" width = "700">
</center>

**1.** 전체적인 Review 코멘트를 작성합니다.

**2.** **Comment, Approve, Request changes** 설정합니다.

   - **Comment** : approve없이 feedback만 작성

   - **Approve** : PullRequest가 문제 없을 때 선택

   - **Request changes** : 작성된 PullRequest에 수정할 점이 있을 때 선택

    ❗️ Pull Request 방향이 JNU-econovation의  → main인지, 라벨을 지정했는지, 타이틀을 작성했는지 등을 확인한 후 만족했을 경우 Approve를 선택합니다.

        



# 7 ) Merge

6명 이상의 동료로부터 Approve를 받은 사람은 Merge 조건을 충족하여 깃요정들로부터 Merge를 받을 수 있습니다. 



### Merge할 동료가 6명 이상에게 **Approve**를 받았는지 확인합니다. 
- Merge할 동료가 6명 이상으로부터 Approve가 채워지지 않았다면 TF팀에게 DM주세요!


