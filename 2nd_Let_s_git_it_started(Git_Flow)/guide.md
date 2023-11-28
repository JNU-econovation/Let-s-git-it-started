# [이론] Git/GitHub이란?

> **여기서 잠깐!✋**
>
> 이 문서는 다양한 사용 경험을 갖춘 사람을 대상으로 하여, 초심자분들이 처음 접했을 때는 조금 어려우실 수도 있습니다.
>
> 1. Git/GitHub에 대해 처음 들어보셨다면?
>    - 자주 사용하는 Git 명령어 위주로 알아보기
> 2. 난 Git/GitHub 좀 써봤다면?
>    - 모든 내용을 다 이해해보기
>
> 다들 처음 Git/GitHub을 접했을 때 어려운 것은 당연해요! 두려워하지 말고 Git/GitHub을 도전해보아요.

**목차 구성**

- [Git/GitHub이란?](#Git/GitHub이란?)
- [주요 용어와 개념](#주요-용어와-개념)
- [시작하기](#시작하기)
- [Git 브랜치](#Git-브랜치)
- [Git 명령어](#Git-명령어)
- [Git Merge](#Git-Merge)
- [Git Rebase](#Git-Rebase)
- [Git Branch 전략](#Git-Branch-전략)

## Git/GitHub이란?

- Git: 버전관리 시스템(프로그램)
- GitHub: 원격저장소, 서버(클라우드)

### Git

Git은 소스코드를 효과적으로 관리하기 위해 개발된 **분산형 버전 관리 시스템(Distributed Version Control)**입니다.

버전 관리 시스템은 왜 필요할까요? 만약 버전관리시스템이 없다면 폴더별로 버전의 이름을 붙여서 하나씩 관리하는 경우가 많았습니다. 마치 저희가 작업 폴더를 `최종`,` 최_최종`,`정말_최종` 이렇게 관리하는 것처럼요! 만약 그렇게한다면 불편한 점들이 생기겠죠?

그래서 등장한 것이...

**Centralized Version Control**입니다.

**서버**에서 히스토리를 관리해서 각 개발자들이 원하는 내용을 업데이트하여 즉각적으로 동기화하는 시스템이죠. 하지만 서버에 문제가 생긴다면 많은 개발자들이 서버에 있는 내용을 확인할 수 없어 일을 못하는 단점이 있습니다.

이 단점을 개선한 것이...

**Distributed Version Control**입니다.

서버에만 히스토리가 있는 것이 아니라 모든 개발자들이 동일한 히스토리를 갖도록 하는거죠. 만약 서버에 문제가 생겨도 각각의 개발자들이 동일한 히스토리를 가지고 있기 때문에, 작업을 이어갈 수 있습니다.

이러한 서버를 제공해주는 서비스로 [GitHub](https://github.com/)과 [Bitbucket](https://bitbucket.org/)과 같은 클라우드가 있습니다.

<details>
<summary>Git은 어떻게 만들어졌을까요?</summary>
<div markdown="1">
</div>
</details>

내용 추가중 입니다.

<!-- 리눅스 창시자 Linus Torvalds는 CVS(Cen)  -->
</details>

### GitHub

그럼 Git과 GitHub을 왜 사용할까요?

- 가장 대중적이며 많이 사용됩니다.
- 오픈소스이므로 무료입니다.
- 모든 동작이 빠릅니다.
- 오프라인으로 사용할 수 있습니다.
- 실수를 고치기가 쉽습니다.
- 각 기능별 브랜치로 쉽고 빠르게 협업 효율을 높일 수 있습니다.

## 주요 용어와 개념

Git/GitHub을 본격적으로 사용해보기 전에 Git의 저장공간인 Working Directory, Stage Area, Repository를 공부해봅시다.

Git은 파일의 변경 사항을 크게 3가지로 구분하여 관리합니다.

- Working Directory: 작업하고 있는 프로젝트 디렉토리
- Stage Area: 커밋을 하기 위해 `git add` 명령어로 추가한 파일들이 모여있는 공간
- Repository: 커밋들이 모여있는 저장소

![Working Directory, Stage Area, Repository](https://user-images.githubusercontent.com/79842129/234326215-059e08bb-99d3-41d5-930b-bff63895d69d.svg)

**Working Directory**

작업 폴더로 Git으로 관리할 프로그램의 소스나 파일들이 위치하는 공간입니다. `git init` 명령을 이용해 초기화 작업을 실행하면 Repository가 생성됩니다.

![Initialize 이미지](https://user-images.githubusercontent.com/79842129/234326580-ca9ba3b2-e428-431c-aaeb-b8e959eda715.svg)

**Repository**

소스나 파일들의 저장소입니다. Working Directory에서 이루어지는 모든 작업 정보가 저장되는 곳입니다. Repository 저장소에 있는 정보들은 Working Directory 내에 `.git` 폴더안에서 관리됩니다.

Git은 **local Repository**, **remote Repository** 두 종류의 저장소로 구분됩니다.

![로컬 저장소와 원격 저장소 이미지](https://user-images.githubusercontent.com/79842129/234327138-cd325688-f492-4a23-939c-8f0e06082679.svg)

- 로컬 저장소(Local Repository)

  **내 PC**에 파일이 저장되는 개인 전용 저장소입니다.

- 원격 저장소(Remote Repository)

  파일이 **원격 저장소 전용 서버**에서 관리되며 여러 사람과 공유하기 위한 저장소입니다.

자신의 PC 저장소에서 작업하다가 작업한 내용을 공유하고 싶을 때 원격 저장소에 업로드하면 되겠죠? 물론 원격 저장소에서 다른 사람이 파일을 로컬 저장소로 가져올 수도 있습니다.

## 시작하기

이제 Git을 본격적으로 사용해봅시다.

### Git 설치

Git을 사용하려면 자신의 컴퓨터에 `git`을 설치해야 합니다. https://git-scm.com/ 에 접속하여 자신이 사용하는 운영체제에 맞는 설치파일을 다운로드합니다.

Git을 비롯해 최근 개발에 많이 사용되는 방식은 CLI(Command Line Interface)를 사용하는 것입니다.

즉, 윈도우의 [GUI(Graphic User Interface)](https://ko.wikipedia.org/wiki/%EA%B7%B8%EB%9E%98%ED%94%BD_%EC%82%AC%EC%9A%A9%EC%9E%90_%EC%9D%B8%ED%84%B0%ED%8E%98%EC%9D%B4%EC%8A%A4) 환경이 아니라 Terminal 혹은 cmd와 같은 콘솔 화면에서 텍스트를 직접 타이핑해서 작업하는 방식을 말합니다.

- Windows는 Git bash를, Mac은 터미널을 사용합니다.

### 환경 설정

처음 git을 사용할 때 사용자 이름과 email 주소를 지정해야 합니다.

```bash
git config --global user.name "이름"
git config --global user.email "이메일주소"
```

### Repository 생성

#### Local Repository 생성

작업 디렉토리를 생성하고 git repository로 사용하도록 초기화 작업을 진행합니다. 작업 디렉토리는 사용자의 홈디렉토리나 별도로 관리하는 경로에 저장소를 만들고 시작합니다.

```bash
mkdir test	# mkdir: make_directory, test 디렉토리를 생성한다.
cd test			# cd: change_directory, test 디렉토리로 이동한다.
git init		# 작업 디렉토리로 설정한다.
```

/_ 이미지 추가_/

#### Remote Repository 생성

공통으로 관리할 저장소를 사용하기 위해, Remote Repository를 생성합니다. 우리에게 가장 친숙한 Github에서 만들 수 있습니다.

[공식문서](https://docs.github.com/en/get-started/quickstart/create-a-repo)를 참고해 만들어 보세요.

#### Remote Repository 연결

앞에서 원격 저장소를 소개했죠?

우리는 github 서버에 Working Directory에서 작업한 내용을 관리하려고 합니다. 이 작업을 하기 위해서 github에 remote repository를 생성해야 합니다.

## Git 브랜치

Git의 최고 장점이라고 평가되는 브랜치는 무엇일까요?

개발을 하다보면 코드를 여러 개 복사하고 원래 코드와 상관없이 독립적으로 개발을 진행해야 하는 상황이 생길 수 있습니다. 예를들어 현재 개발된 홈페이지에 A와 B가 새로운 기능을 추가하고 싶은 것처럼요!

기본적으로 Git은 `main` 브랜치를 생성합니다. 처음 커밋하면 이 `main` 브랜치는 생성된 커밋을 가리킵니다. 이후 커밋이 생성되면 `main` 브랜치는 자동으로 가장 최신 커밋을 가리킵니다.

![브랜치 커밋 히스토리 이미지 추가](https://user-images.githubusercontent.com/79842129/234327942-1504dd26-f83e-4584-a02a-f0182167b636.svg)

HEAD는 현재 내가 선택한 브랜치의 최신 커밋에 대한 포인터를 말합니다. 이 그림에서는 main 브랜치의 가장 최신 커밋인 `5f832d`를 가리키겠네요!

> **브랜치 생성**

새로운 작업을 하기위해 브랜치를 생성해 봅시다. 생성한 브랜치는 하나의 작업 단위로 가져갈 수 있겠죠?

```bash
git branch {생성할 브랜치 이름}
```

![브랜치 생성 이미지](https://user-images.githubusercontent.com/79842129/234328417-c6861bb7-8035-4611-a050-c60776ba8bc7.svg)

새로 만든 브랜치도 지금 작업하고 있던 최신 커밋을 가리키는 것을 확인할 수 있습니다.

> **브랜치 이동**

이제 생성된 브랜치로 이동해볼까요?

switch 명령어를 이용해서 생성된 브랜치로 이동해봅시다.

```bash
git switch {이동할 브랜치 이름}
```

![checkout 브랜치 이미지](https://user-images.githubusercontent.com/79842129/234328717-930253fc-5050-475d-8c9c-54bb155efdfd.svg)

+) `git switch -b {브랜치 이름}` 명령어를 사용하면, 브랜치를 생성하고 동시에 이동할 수 있답니다.

### 브랜치는 왜 필요할까요?

여러명이 동시에 개발하는 상황을 떠올려볼까요? 아마 누군가는 '회원 가입'을, 누군가는 '채팅 기능'을 만드는 것으로 역할 분담할 수 있을 것입니다. 여러 명이서 동시에 작업할 때 다른 사람의 작업에 영향을 주거나 받지 않도록 각자 작업 브랜치를 만들고 메인 브랜치에 자신의 변경 사항을 적용합니다.

이렇게 하면 다른 사람의 작업에 영향을 받지 않고 독립된 작업을 수행할 수 있고, 작업이 완료되면 그 결과를 하나로 모을 수 있겠죠.

이러한 방식으로 작업하면 '작업 단위', 즉 브랜치로 그 작업 기록을 중간 중간 남기게 되므로 문제가 발생했을 때 원인이 되는 작업을 찾고 그에 따른 대책을 쉽게 세울 수 있습니다.

![브랜치 필요성](https://user-images.githubusercontent.com/79842129/234329319-d880441e-5c2b-4af0-94f8-c87e88b4e9f6.svg)

+) 이처럼 브랜치를 생성할 때 규칙을 만들어 효과적으로 협업하는 방법을 [Git 브랜치 전략](https://inpa.tistory.com/entry/GIT-%E2%9A%A1%EF%B8%8F-github-flow-git-flow-%F0%9F%93%88-%EB%B8%8C%EB%9E%9C%EC%B9%98-%EC%A0%84%EB%9E%B5)이라고 합니다.

## Git 명령어

### git init

현재 작업 디렉토리를 git으로 관리하기 위한 명령어입니다.

1. 저장소로 사용하고자 하는 디렉토리로 이동하여 `git init`을 입력합니다.

   ```bash
   git init
   ```

2. `.git` 디렉토리가 생성됩니다. Git이 현재 디렉토리의 변동사항을 계속 파악하고 있다는 의미입니다.

   - `.git` 디렉토리는 숨겨진 디렉토리입니다. 일반적인 `ls` 명령만으로는 디렉토리가 조회되지 않습니다. 따라서 `ls -al` 을 입력하여 확인 가능합니다.

git init을 하기 전 디렉터리 모습입니다.
​<img width="739" alt="image" src="https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/daaad882-838b-41cc-b39e-b30d77481d0d">

이후 git init 명령어를 cmd창에 입력해봅시다.
<img width="568" alt="image" src="https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/718051f1-777a-4691-a260-6226eacb118a">

이후 아래와 같이 .git 디렉터리가 생성됨을 알 수 있습니다.
<img width="733" alt="image" src="https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/7775481b-a13e-47bd-9e54-b1499dab4edd">

### git remote add {등록 이름} {원격 저장소 주소}

`git init` 명령어로 작업 디렉토리에서 git을 사용할 수 있도록 설정했습니다. github을 사용하는 이유가 원격 저장소에 작업 내용을 기록하기 위함이라고 했죠? 그렇기 위해서는 **원격 저장소와 로컬 작업 저장소를 연결**해야 합니다.

```bash
git remote add {등록 이름} {원격 저장소 주소}
```

- 등록 이름: [원격 저장소 주소]의 별명(alias)라고 생각하면 됩니다. 매번 긴 원격 저장소 주소를 입력해야 한다면 매우 귀찮을 거예요. 우리는 관례적으로 원격 저장소의 별명으로 `origin`을 사용한답니다.
  - git clone을 이용하여 프로젝트를 가져올 경우 자동으로 remote 저장소의 이름이 origin으로 등록됩니다.
- 원격 저장소 주소: GitHub repository 주소를 말합니다.

### git clone {원격 저장소 주소} {복제 경로}

GitHub 원격 저장소에 있는 내용들을 로컬에 복제해오는 것을 말합니다.

- 복제 경로(생략 가능): 원격 저장소에 있는 내용들을 로컬에 복제할 경로를 지정하면, 해당 위치에 내용이 복제됩니다.

```bash
git clone {원격 저장소 주소}
```

### git add

작업 디렉토리의 변경 내용을 스테이징 영역에 추가하기 위해 사용하는 명령어입니다.

스테이징 영역은 변경 사항 중에 '저장하고 싶은 부분만 선택해 임시로 저장'할 수 있는 공간인데요. 이미 로컬 저장소와 원격 저장소가 존재하는데, 왜 별도의 공간이 필요한지 궁금하실 것 같네요. 자세한 내용은 [Git의 Staging Area는 어떤 점이 유용한가](https://blog.npcode.com/2012/10/23/git%EC%9D%98-staging-area%EB%8A%94-%EC%96%B4%EB%96%A4-%EC%A0%90%EC%9D%B4-%EC%9C%A0%EC%9A%A9%ED%95%9C%EA%B0%80/)에 정리되어 있으니 참고하시면 좋을 것 같습니다~

> 특정 파일만 스테이징 하기(특정 파일의 변경 사항만 스테이징)

```bash
git add {파일명}
```

> 저장소 내 모든 파일 스테이징 하기(모든 파일의 변경 사항을 스테이징)

```bash
git add .
```

### git commit

`add` 명령어로 변경 내용을 스테이징 영역에 추가했습니다. 그럼 이제 추가되었다는 것을 기록해야겠죠?

`commit`은 파일 및 폴더의 추가/변경 사항을 저장소에 기록하는 명령어입니다. 즉 스테이징된 파일을 저장소로 옮기는 작업입니다.

- `-m` 옵션: `commit` 명령어와 함께 사용하는 옵션입니다. 저장소로 파일을 옮길 때 해당 커밋의 메시지를 작성할 수 있도록 합니다. 메시지는 ""(큰 따옴표) 안에 작성합니다.
- 만약 옵션이 없다면, vim 에디터로 연결되며 한줄로 표현하기 어려운 메시지를 자세하게 설명할 수 있습니다.

```bash
git commit -m "커밋 메시지 내용"
```

커밋 메시지를 작성하는 것은 정말 중요합니다! 마치 역할분담하여 과제할 때, 자신이 맡은 작업물만 달랑 주기보다는 '어떤 작업을 했는지' 설명하는 것처럼요. 그래서 커밋 메시지 규칙도 있답니다.(참고: [How to Write a Git Commit Message](https://cbea.ms/git-commit/))

### git status

Staged, Unmodified 등 파일들의 상태(status)를 확인하는 명령어입니다.

지금까지 add, commit 명령어를 공부하면서 '스테이징 영역'이라는 단어를 들어봤을 것입니다. 또 '변경 사항을 감지하여 기록한다'는 등 이런 이야기도 들어봤을 것입니다.

이처럼 git으로 관리하는 파일들은 다음의 상태(status)를 갖습니다.

**[git으로 관리하는 파일 상태]**

- **Untracked**: Git 저장소에 있지만 Git이 관리하지 않는 상태
- **Tracked**: Git이 관리하는 상태
  - **Unmodified**: 파일이 수정되지 않은 상태
  - **Modified**: 파일이 수정된 상태
  - **Staged**: 스테이징 영역(커밋 직전 저장소)에 올라간 상태

<img width="753" alt="image" src="https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/47850e2a-5ae7-47f0-be43-95e7645e2b90">

만약 1) <u>처음 저장소를 clone</u>해오게 되면, 모든 파일은 **Tracked**이면서 **Unmodified** 상태가 됩니다. 이 상태에서 2) <u>어떤 파일을 수정하면</u> 해당 파일은 **Tracked**이면서 **Modified** 상태가 됩니다. 실제로 3) <u>원격 저장소에 변경 내용을 반영하기 위해서</u> 수정한 파일을 **Staged** 상태로 만들고, Staged 상태의 파일을 **commit**해야 합니다.

> 변경 사항이 없을 경우
> Remote Repository를 Clone한 상황
> <img width="873" alt="image" src="https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/461598c8-25f4-4a36-b17d-dfffca2e294f">

> 변경 사항이 있을 경우

clone한 local repository에서 새로운 파일을 생성하였습니다.
이 경우 새로운 파일은 아직 Git이 인식하지 못 하는 파일이기 때문에 Untracked File(추적하지 않는 파일)로 뜹니다.
<img width="918" alt="image" src="https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/024e32bb-f0da-4203-9ba0-98b26b5d5f95">

> git add를 진행하지 않은 상태

[변경 사항이 없을 경우] 카테고리와 다른점을 찾아보셨나요?
바로, 이번에는 Untracked File이 아니라 **커밋하도록 정하지 않은 변경 사항** 이 뜨는 것을 확인할 수 있습니다.

이 경우는 Tracked File이지만, 변경사항이 존재할 경우 아래와 같은 응답이 발생합니다.
<img width="589" alt="image" src="https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/4a58732e-acb1-4f9c-93df-63139dcabe8e">

> git add를 진행한 상태
> staged(스테이징 됨) 상태가 된 것을 확인할 수 있습니다. 즉 커밋할 준비가 된 상태입니다.
> <img width="617" alt="image" src="https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/f5049b6d-25ee-4507-95d9-63398d9780d6">

### git branch

위에서 [브랜치](#Git-브랜치)에 대해 공부했죠? 관련 명령어를 알아봅시다.

> 브랜치 생성하기

```bash
git branch {브랜치명}
```

<img width="1088" alt="image" src="https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/e225bad2-de88-4aca-8179-dee042771546">

> 브랜치 확인하기

```bash
git branch
```

<img width="721" alt="image" src="https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/5e05c2c4-de77-40e1-bf0d-694caf20545a">
<img width="338" alt="image" src="https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/1fecfcdc-3e05-420e-bdd8-828bb6bddbc1">

> 브랜치 삭제하기

```bash
git branch -d {브랜치명}
```

주의할 점은 현재 삭제할 브랜치에 있으면 안 됩니다.
<img width="942" alt="image" src="https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/be2b8c2c-ac59-4734-892a-6b098c37d607">

삭제할 브랜치가 아닌 다른 브랜치로 이동 후 브랜치를 삭제해야합니다.
<img width="840" alt="image" src="https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/a2cc3f5e-ec1e-405b-b988-2dda51da4eb0">

### git switch

현재 작업중인 브랜치를 가리키는 포인터를 HEAD라고 합니다.
작업중인 브랜치에서 다른 브랜치로 이동하려면 HEAD를 이동시키면 됩니다.

> 브랜치 이동하기

```bash
git switch {브랜치명}
```

<img width="764" alt="image" src="https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/3b3dc99d-9631-432a-a529-376f5f78dcb3">

기존 main 브랜치에서 /_ 변경된 브랜치명_/으로 이동된 것을 확인할 수 있습니다.

브랜치 이동은 현재 존재하는 브랜치들 중에서 이동할 수 있습니다. 만약 switch 하려는 브랜치가 없다면 이동할 수 없겠죠.
<img width="778" alt="image" src="https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/4d4fff64-1e89-4fbe-b7fe-eefe89a68149">

> git pull origin {브랜치명}
> remote repo에서 데이터를 가져올 뿐만 아니라(git fetch) 변경된 내용을 local repo의 내용과 병합한다.(git merge)
> <img width="574" alt="image" src="https://github.com/JNU-econovation/gitPractice/assets/88534959/cef0ec2a-c9f3-4397-8eb2-9747a082cd12">

> git log

저장소의 커밋 히스토리를 시간순으로 볼 수 있다.
<img width="707" alt="image" src="https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/1642b5cc-335f-4bfc-827f-311de97dd110">
<img width="829" alt="image" src="https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/5edb1d85-c78b-414d-8795-bc568b2a6703">

<img width="773" alt="image" src="https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/ae4b50f8-8439-4f5f-a82a-ec0b832b5b3f">
<img width="961" alt="image" src="https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/a9b1a7d2-2cfe-4112-ab9b-1f3fa117caad">

### git diff

해당 명령어를 사용하면 Working Directory와 Staging Area 사이의 차이를 확인하기 위한 명령어
<img width="697" alt="image" src="https://github.com/JNU-econovation/weekly_presentation/assets/88534959/639c6d63-8637-45c2-abab-f7ca59857907">
<img width="1222" alt="image" src="https://github.com/JNU-econovation/weekly_presentation/assets/88534959/f12bd52d-787c-4810-bb51-867999a589d0">

### git reset [mode] [commit]

해당 명령어는 현재 브랜치 헤드를 [commit]으로 재설정하고 [mode]에 따라 인덱스([commit]의 트리로 재설정)와 작업 트리를 업데이트할 수 있습니다. 작업 전, ORIG_HEAD는 현재 분기의 끝으로 설정됩니다. [mode]를 생략하면 기본값은 --mixed입니다. [mode]는 다음 중 하나이어야 합니다.

- soft  
  인덱스 파일이나 작업 트리를 전혀 건드리지 않습니다(하지만 모든 모드와 마찬가지로 헤드를 [commit]으로 재설정합니다). 이렇게 하면 변경된 모든 파일이 "커밋할 변경 사항"으로 남게 됩니다.

- mixed  
  인덱스는 재설정하지만 작업 트리는 재설정하지 않고(즉, 변경된 파일은 보존되지만 커밋으로 표시되지 않음) 업데이트되지 않은 내용을 보고합니다. 이것이 기본 동작이다.

- hard  
  인덱스와 작업 트리를 재설정합니다. <commit> 이후 작업 트리에서 추적된 파일에 대한 모든 변경 사항은 삭제됩니다. 적되지 않은 파일이나 디렉토리는 추적된 파일을 작성하는 과정에서 간단히 삭제됩니다.

### Git Merge

명명된 커밋(현재 브랜치에서 히스토리가 갈라진 시점부터)의 변경 내용을 현재 브랜치에 통합하는 과정입니다. 이 명령은 다른 리포지토리의 변경 내용을 통합하기 위해 git pull에서 사용되며, 한 브랜치의 변경 내용을 다른 브랜치에 병합하기 위해 수동으로 사용할 수도 있습니다.

다음 히스토리가 존재하고 현재 브랜치가 "마스터"라고 가정합니다.

<img width="242" alt="image" src="https://github.com/JNU-econovation/Let-s-git-it-started/assets/86696759/b0a4f8a4-370a-4d90-b1e6-2de7df360e21">

그런 다음 "git merge topic"은 토픽 브랜치가 마스터(즉, E)에서 분기된 이후부터 마스터 위에 있는 현재 커밋(C)까지의 변경 내용을 반영하고, 두 부모 커밋의 이름과 변경 내용을 설명하는 사용자의 로그 메시지와 함께 결과를 새 커밋에 기록합니다.

작업 전에 ORIG_HEAD는 현재 브랜치(C)의 끝으로 설정됩니다.

<img width="279" alt="image" src="https://github.com/JNU-econovation/Let-s-git-it-started/assets/86696759/379c46a5-c0e0-4143-87c3-493dddb915bf">

두 번째 구문("git merge --abort")은 병합으로 인해 충돌이 발생한 후에만 실행할 수 있다. git merge --abort는 병합 프로세스를 중단하고 병합 전 상태를 재구성하려고 시도한다.

그러나 병합이 시작될 때 커밋되지 않은 변경 사항이 있는 경우(특히 병합이 시작된 후 변경 사항이 추가로 수정된 경우) `git merge --abort`는 경우에 따라 원래(병합 전) 변경 사항을 재구성할 수 없습니다.

## Git Branch 전략

### 개요

### 0. git branch 전략이 뭔가요?

git branch 전략은 여러 개발자가 하나의 저장소를 사용하는 환경에서 저장소를 효과적으로 활용하기 위해 나온 개념입니다.

브랜치 전략이 없다면 어떤 브랜치에 push 해야 하는지, 또한 어떤 브랜치에서 pull을 해와서 개발을 시작해야 하는지 등부터 많은 혼란을 야기할 것입니다.

이 문서에서는 Git Flow, GitHub Flow, GitLab Flow, Fork와 PR의 4가지 전략에 대해서 알아봅니다.

### 1. Git Flow

git flow 전략에는 항상 유지되는 메인 브랜치들`(master, develop)`과 일정 기간동안만 유지되는 보조 브랜치들`(feature, release, hotfix)`이 있습니다. 보조 브랜치들은 필요할 때마다 생성되고, 역할을 다하면 삭제됩니다. 이 보조 브랜치 덕분에 병렬적인 업무가 가능해집니다.

<p align="center"><img width="700" alt="Git Flow" src="https://github.com/Hyeonz1/Android-Jetpack-Fundamentals-Training/assets/114472483/3dc8b3c3-61c2-40de-bc49-5f1a3e0ec5b3"></p>

- master: 제품으로 `출시`될 수 있는 브랜치
- develop: 다음 출시 버전을 대비하여 `개발`하는 브랜치
- feature: `기능`을 개발하는 브랜치
- release: 배포를 위해 master 브랜치로 보내기 전에 먼저 `QA`(품질검사)를 하기 위한 브랜치
- hotfix: 출시 버전에서 발생한 `버그`를 수정하는 브랜치

각각의 브랜치를 자세히 알아봅시다.

**메인 브랜치**

<p align="center"><img width="500" alt="메인 브랜치" src="https://github.com/Hyeonz1/Android-Jetpack-Fundamentals-Training/assets/114472483/63516254-9b8b-4525-8036-ce0a465970b7"></p>

- main branch에는 **master branch**와 **develop branch**가 있습니다.
- 처음 master 브랜치에서 분기하는 것으로 시작하며, 다음 버전 구현이 완료되어 배포를 하고 싶을 때 master로 다시 합치는 방식으로 운영됩니다.
- develop 브랜치는 통합 브랜치의 역할을 하며, 평소에는 이 브랜치를 기반으로 개발을 진행합니다.

**보조 브랜치**

1. **Feature 브랜치**

<p align="center"><img width="500" alt="Feature 브랜치" src="https://github.com/Hyeonz1/Android-Jetpack-Fundamentals-Training/assets/114472483/14eb6efa-3b6e-4a10-989c-e2b8d71f6316"></p>

- 하나의 기능을 개발하기 위한 브랜치입니다. develop 브랜치에서 생성하며, 기능이 개발 완료되면 다시 develop 브랜치로 merge 됩니다.
- 브랜치명은 보통 팀 컨벤션을 따릅니다. `ex) feature/login, feature/#1(issue 번호)`

2. **Release 브랜치**

<p align="center"><img width="500" alt="Release 브랜치" src="https://github.com/Hyeonz1/Android-Jetpack-Fundamentals-Training/assets/114472483/c4155bff-df63-4c0a-b326-c771cab7c64b"></p>

- 소프트웨어 배포를 준비하기 위한 브랜치입니다. 버전 이름을 수정하거나 배포전 사소한 버그를 수정하기 위해 사용됩니다.
- develop 브랜치에서 생성하며, 배포 준비가 완료되었다면 master브랜치에 머지합니다. 이때, master 브랜치에는 태그를 이용하여 버전을 표시합니다. release 브랜치에서 기능을 점검하며 발견한 버그 수정 사항은 develop 브랜치에 대해서도 merge 작업을 수행해줍니다.
- release 브랜치가 배포를 위한 준비를 하는 동안 develop 브랜치는 기능 개발을 지속할 수 있다는 장점이 있습니다.
- 네이밍은 주로 `release-1.2, release/1.2` 과 같은 형태로 생성합니다.

3. **Hotfix 브랜치**

<p align="center"><img width="500" alt="Hotfix 브랜치" src="https://github.com/Hyeonz1/Android-Jetpack-Fundamentals-Training/assets/114472483/5438b8fb-d94e-4ff1-a6d6-28c017f6926b"></p>

- 이미 배포된 버전에 수정사항이 생겼을 경우, hotfix 브랜치를 사용하여 문제를 해결합니다.
- master 브랜치에서 분기하여 hotfix 브랜치를 생성하며, 문제 해결이 완료되면 master과 develop 브랜치에 둘다 머지합니다. 이때 tag를 통해 관련 정보를 기록해 둡니다.
- release 브랜치와 마찬가지로 hotfix 브랜치를 따로 운용함으로써, 핫픽스 업무와 관련없는 팀은 병렬적으로 기능 개발을 할 수 있습니다.
- 네이밍은 보통 `hotfix/v1.0.1` 과 같은 형태로 생성합니다.

### 2. GitHub Flow

Git Flow는 명시적으로 버전관리가 필요한 스마트폰 어플리케이션, 오픈소스 라이브러리/프레임워크 등의 프로젝트에 적합합니다.
**웹 어플리케이션은 특성상 사용자는 항상 최신의 단일 버전**만을 사용합니다. 즉, 여러 버전을 병렬적으로 지원할 필요가 없습니다. 또한 웹 어플리케이션은 하루에 몇번이고 릴리즈될 수 있습니다. 이런 특성을 바탕으로 웹 어플리케이션 개발에는 이제부터 소개할 GitHub flow 를 사용하는 것이 더 나은 방법일 수 있습니다.

<p align="center"><img width="700" alt="GitHub Flow" src="https://github.com/Hyeonz1/Android-Jetpack-Fundamentals-Training/assets/114472483/3fd7e770-6063-48cc-b3b0-7a8ce68236f2"></p>

Github Flow는 Git Flow와 다르게 굉장히 간단한 구조이며 Github 환경에서 사용하기 적합한 브랜치 전략이기도 합니다. 또한 수시로 배포가 일어나며, CI와 배포가 자동화되어있는 프로젝트에 유용합니다.

GitHub Flow에서 사용하는 브랜치는 다음과 같습니다.

- **master branch**

  - 배포를 위한 branch
  - master 브랜치는 항상 최신 상태며, **stable** 상태로 product에 배포되는 브랜치 입니다.
    - 즉, master의 **모든 커밋은 언제 배포하든 문제가 없어야 하고 언제든 브랜치를 새로 만들 수 있어야** 합니다. master 브랜치의 모든 커밋은 **빌드가 되고, 테스트를 통과**해야합니다.
    - 테스트는 로컬에서 하는 것이 아니라 브랜치를 push 하고 Jenkins로 테스트 합니다.
      _[Jenkins](https://www.jenkins.io/) : 개발 작업 자동화 뿐 아니라 소스 코드 저장소 대한 지속적인 통합과 지속적인 배포 환경을 구축하기 위한 간단한 방법을 제공하는 도구_

- **Topic branch**
  - **새로운 기능**을 개발할 때에는 **Topic 브랜치**를 master 브랜치로부터 생성합니다. Git Flow의 Feature 브랜치와 동일한 역할을 합니다.
  - 체계적인 분류 없이 브랜치 하나에 의존하기 때문에 **브랜치 이름을 통해 의도를 명확하게** 드러내는 것이 매우 중요합니다.
  - 브랜치 명으로는  **`user-content-cache-key`**, **`submodules-init-task`**, **`redis2-transition`** 등이 있습니다.
  - Topic 브랜치의 커밋은 기능이 완성되지 않았더라도 **꾸준히 Push** 합니다. 노트북 분실, 작업 컴퓨터의 고장등의 위험으로 코드가 유실되는 것을 막아주고, 구성원 모두가 끊임없이 커뮤니케이션 할 수 있게 해줍니다.

### 3. GitLab Flow

<p align="center"><img width="500" alt="GitLab Flow" src="https://github.com/Hyeonz1/Android-Jetpack-Fundamentals-Training/assets/114472483/6870bcd3-fd90-4231-990c-f181f75b5900"></p>

GitLab Flow는 GitFlow와 GitHub Flow의 **절충안**으로 등장한 git branch 전략입니다. GitHub Flow와 비교하였을 때 **배포, 릴리즈 등의 조금 복잡한 이슈를 보완**할 수 있어요.

GitLab Flow에서 사용하는 브랜치는 다음과 같습니다.

- **feature 브랜치**  
  GitLab Flow의 **모든 기능 구현**은 feature 브랜치에서 시작합니다. feature 브랜치는 master 브랜치에서 분기하고, 또한 feature 브랜치에서 구현한 기능을 master 브랜치로 merge합니다.
- **master 브랜치**  
  Git Flow의 develop 브랜치와 동일한 역할을 하는 브랜치입니다. feature 브랜치에서 master 브랜치로 병합된 기능에 대해 **test를 진행**합니다.

- **production 브랜치**  
  Git Flow의 master 브랜치와 동일한 역할을 하는 브랜치입니다. 테스트가 끝난 **기능을 배포**합니다.

- **pre-production 브랜치**  
  master 브랜치와 production 브랜치의 사이에 있는 브랜치입니다. master의 변경 사항을 바로 production에 병합하여 배포하는 대신, **test server에 배포하여 통합 테스트를 진행**하거나 **시간을 두고 반영**하도록 합니다.

### 4. Fork와 Pull Request

<p align="center"><img width="700" alt="Fork와 Pull Request" src="https://github.com/Hyeonz1/Android-Jetpack-Fundamentals-Training/assets/114472483/0e3b16c4-b039-4666-bf49-673e8bdaf855"></p>

fork와 Pull Request 전략에서는 **브랜치 대신 fork와 Pull Request 기능**을 활용하여 협업합니다.

- fork는 프로젝트 전체를 **나의 원격 Repository로 복제**할 수 있는 기능입니다.
- Pull Request를 사용하여 **원래 프로젝트 Repository로 merge 요청**을 보낼 수 있습니다. 원래 프로젝트의 관리자는 내가 merge를 요청한 코드를 보고 merge를 허용 여부를 결정합니다.
- fork와 헷갈릴 수 있는 명령어로 clone이 있습니다. clone은 **특정 원격 repository를 내 노트북에 복사**하여 새로운 로컬 저장소를 만드는 명령어입니다. 반면 fork는 **특정 원격 repository를 나의 원격 repository로 복제**해오는 명령입니다.

**우아하게 Pull Request 사용하기**

이번 시간에는 우아하
