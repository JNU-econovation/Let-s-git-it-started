# [실습] Let's git it started 시작하기


<aside>
🙌 <b>[이론편]</b>(이론편 링크) 잘 확인하고 오셨나요?**

이번에는 앞에서 배운 내용을 바탕으로 직접 행사를 참여하는 실습을 진행하려고 합니다. 상세한 설명을 확인하고 싶으신 분들은 [이론편](이론편 링크)을 참고해주세요! 

</aside>

Let's git it started행사는 자신을 소개하는 글을 작성하여 [1) Pull Request하기](#pull-request), 서로의 소개글을 읽으면서 궁금하거나 공감가는 내용은 [2) Review 기능을 이용해 소통하기](#review), 6명 이상의 리뷰어로부터 승인 받을 시 [3) Merge](#merge) 받는 단계로 이루어집니다. 

# Pull Request

Pull Request(PR)은 자신이 변경한 내용을 동료에게 전달하는 과정입니다. 이 실습에서는 자신의 자기소개를 동료들에게 공유하기 위해 Pull Request를 만드는 거죠!

1. [개인 로컬(local) 저장소와 원격(remote) 저장소 연결](#step1-개인-로컬local-저장소와-원격remote-저장소-연결)
2. [개인 branch 생성](#step2-개인-branch-생성)
3. [수정 작업 후 원격저장소에 반영(push)](#step3-수정-작업-후-원격저장소에-반영push)
4. [Pull Request 생성](#step4-pull-request-생성)

## Step1. 개인 로컬(local) 저장소와 원격(remote) 저장소 연결

> 로컬(local) 저장소와 [let-s-git-it-started](https://github.com/JNU-econovation/Let-s-git-it-started)저장소를 연결하는 과정입니다.
> 

![repository connect](https://user-images.githubusercontent.com/79842129/229303401-477ed077-1075-4b93-ab1c-2d0c7267f2ae.png)

<figcaption align = "center">
<b>그림1</b> 개인 로컬 저장소와 원격 저장소 연결
</figcaption>


### 1. **git init**
    
자신의 PC에 작업을 진행할 디렉토리를 생성한 후 생성된 디렉토리에서 명령을 실행합니다. 


=======
- 디렉토리명과 원격저장소명은 달라도 괜찮습니다.

```bash
$ git init
```

이 폴더에서 git을 실행할거야! 라는 의미입니다.

- `ls -al`을 통해 숨김 디렉토리를 확인하면 **.git 디렉토리가** 생성된 것을 확인할 수 있습니다.

### 2. **git remote add** 

원격 저장소를 local git에 등록합니다. 

원격 저장소 주소 : [https://github.com/JNU-econovation/Let-s-git-it-started](https://github.com/JNU-econovation/Let-s-git-it-started)

```bash
$ git remote add origin https://github.com/JNU-econovation/Let-s-git-it-started
```

원격 저장소 주소 [https://github.com/JNU-econovation/Let-s-git-it-started](https://github.com/JNU-econovation/Let-s-git-it-started)을 `origin`이라는 이름으로 local git에 등록하는 과정입니다. `origin`은 등록할 긴 **원격 저장소 주소를 대체할 별명**인데요. 일반적으로 `origin`이 많이 사용됩니다.
    
### 3. **git pull**

등록한 원격 저장소에 담긴 내역을 local에 가져옵니다. 

```bash
$ git pull origin main
```

등록된 원격 저장소 주소(`origin`이 되겠죠?)의 main branch에 담긴 내용들을 가져오겠다 라는 의미입니다. 작업하고 있는 local 저장소를 최신 상태로 업데이트하는 과정이기 때문에 협업에서 중요한 과정입니다.

- `ls` 명령어를 실행하시면 원격 저장소에서 불러온 내용들을 확인할 수 있습니다.
    
>    <aside>
>    🔎 <b>git clone</b>
>
>    `git clone {GitHub 원격 저장소 주소}` 사용 시 GitHub 원격 저장소 주소의 저장소가 복제됩니다.  
>     Git 저장소를 관리하는 **.git** 디렉토리와 GitHub 원격 저장소 데이터가 모두 담겨 있음을 확인할 수 있습니다.

>   </aside>
    

## Step2. 개인 branch 생성

> 연결된 저장소의 main branch 기준으로 개인 branch를 생성하는 과정입니다.


 ![making branch](https://user-images.githubusercontent.com/79842129/229303414-938ec561-4b6f-427c-8c40-09859b0d661f.png)
 <figcaption align = "center">
 <b>그림2</b> branch의 생성과 merge
 </figcaption>
 <br></br>

각자의 branch를 생성하여 자기소개를 작성합니다. branch는 한국어로 나뭇가지라는 뜻인데요. 위 그림처럼 main branch를 기준으로 각자의 branch를 생성해 그곳에서 작업한 후 최종적으로 main branch에서 병합(merge)하는 것이 이번 미션의 목표입니다.

 

### 1. **git branch** 
    
자신의 branch를 생성합니다.

```bash
$ git branch {자신의_github_ID} main
```

![branch merge](https://user-images.githubusercontent.com/79842129/229303404-4a4e7433-d65d-4734-865f-791b986b3bca.png)
<figcaption align = "center">
<b>그림3</b> branch 생성
</figcaption>
<br></br>


main branch에서 나오는 branch를 만들 것이고 생성된 branch 이름은 무엇이라고 하겠다 라는 의미입니다.  예를 들어 `git branch econo main`라는 명령을 하면 main branch에서 econo이라는 branch를 생성하겠다 라는 말이겠죠? 

- 본 실습에서 생성된 branch 이름은 **자신의 Username**으로 만들어주세요!
<br></br>

`git branch --all` 명령어를 활용해서 방금 생성된 branch를 확인할 수 있습니다. 

![git branch econo main](https://user-images.githubusercontent.com/79842129/229303403-3bb64ecc-f96f-419d-be2f-e78f6ca8d7d8.png)

<figcaption align = "center">
<b>그림4</b> git branch --all을 통해 branch를 확인한 모습
</figcaption>
<br></br>

    
### 2. **git checkout**
    

`git status` 명령어를 통해 현재 상태를 확인하시면 **On branch main**라는 텍스트를 확인할 수 있는데요. 저희는 아직 main branch에 있습니다. 이제 자기소개를 작성하기 위해 방금 생성한 branch로 이동하겠습니다.

```bash
$ git checkout {이동할_branch_이름} 
```

![checkout](https://user-images.githubusercontent.com/79842129/229303409-63f85305-b70c-4865-ba1a-ed3d7b50bcd9.png)
<figcaption align = "center">
<b>그림5</b> checkout을 사용한 모습
</figcaption>
<br></br>

마찬가지로 `git status`명령을 사용하시면 이동한 branch 이름을 확인할 수 있습니다.
    
>    <aside>
>    🔎 <b>git checkout -b {이동할 branch 이름}</b>
>    
>    `git checkout -b {이동할 branch 이름}` 사용 시 branch 생성과 동시에 생성한 branch로 이동할 수 있습니다. 
    
>    </aside>
    

## Step3. 수정 작업 후 원격저장소에 반영(push)

> 로컬(local) 저장소에서 자기소개를 작성한 후, 원격 저장소에 반영(push)하는 과정입니다.
> 

### 1. profile 폴더에 있는 profile.md 파일을 복제합니다. 복제하여 생성된 파일 이름을 자신의 **github id**로 수정합니다.
- profile.md는 절대 지우지 마세요!

![git_folder](https://user-images.githubusercontent.com/79842129/229303412-cb14ffa2-ee45-4283-9f6c-55ba691119a3.png)

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
    

### 3. **git add** 

자신을 소개하는 글을 작성하셨나요? 

이제 여러분의 local 저장소 변경사항(글 작성)을 Github에 반영할 차례입니다. 

```bash
$ git add .
```

`git status` 명령어로 확인해볼까요? 아마 여러분이 방금 생성한 md파일이 새롭게 생성되었음을 확인할 수 있을 것입니다. 

![git status](https://user-images.githubusercontent.com/79842129/229303411-50e19f99-6080-40c1-bd67-e53b49761a6d.png)
<figcaption align = "center">
<b>그림7</b> git status를 사용하여 확인한 모습
</figcaption>
<br></br>
    
### 4. **git commit** 

    
변경 사항을 기록하는 것을 커밋이라고 합니다. 

이때 어떤 변경 사항이 있는지 설명하는 것을 커밋 메시지라고 하는데요. 커밋은 이력을 남기는 중요한 작업이므로 커밋 메시지는 필수입니다. 

- 원활한 협업을 위해서 올바른 커밋 메시지를 작성하는 것이 중요합니다. 함께 협업하는 동료와 함께 커밋 메시지 컨벤션을 만들어 협업해보세요!

```bash
$ git commit -m "{남길 commit message}"
```

![add,commit](https://user-images.githubusercontent.com/79842129/229303407-741ed311-0d1e-46b3-92cd-06557997b248.png)
<figcaption align = "center">
<b>그림8</b> add와 commit
</figcaption>
<br></br>

저는 "add: econo.md" 라는 커밋 메시지와 함께 변경 사항을 기록했습니다. 
    

### 5. **git push**

이제 업로드할 준비는 다 완료되었습니다. 지금까지는  local에서 변경 이력을 남긴 것이고 이제 이것을 원격(remote) 저장소에 전송합니다.

```bash
$ git push origin {branch명}
```

![git_push](https://user-images.githubusercontent.com/79842129/229303408-e9086596-8b79-4e2e-a289-0f82642e1044.png)
<figcaption align = "center">
<b>그림9</b> push
</figcaption>
<br></br>

`origin`은 원격저장소(remote) 주소를 의미하는데요. `origin`이라는 원격저장소에 branch에서 남긴 코드 변경 이력을 올리는 과정입니다.

예를 들어, 저는 econo라는 branch에서 자기소개글을 작성했고 이 변동사항을 origin에 올리기 때문에 명령어는 다음과 같습니다.

```bash
$ git push origin econo
```

명령어 실행 결과 새롭게 branch가 생성되고, 해당 branch로 이동하였을 때 local에서 작업한 내용이 업로드 되었음을 확인할 수 있습니다.

![github_branch](https://user-images.githubusercontent.com/79842129/229303415-b27836fc-e989-4f5b-bacf-38c09deb695a.png)
![branch_upload](https://user-images.githubusercontent.com/79842129/229303420-45902245-208f-4352-b971-3a715426b5c9.png)
<figcaption align = "center">
<b>그림10</b> GitHub에서 branch를 확인한 모습
</figcaption>
<br></br>


    

## Step4. Pull Request 생성

> 자신이 반영한 내역(자기소개 작성 후 추가)을 공유하는 과정입니다.
> 
> - 개발할 때 코드 변경 사항을 반영하고 싶을 때 기존 프로젝트 소유자에게 요청하는 작업을 ***Pull Request한다*** 라고 합니다.

이제 모든 준비가 다 되었습니다. 변경한 내용을 전달해보아요!

### 1. [https://github.com/JNU-econovation/Let-s-git-it-started](https://github.com/JNU-econovation/Let-s-git-it-started) 에서 Pull requests 탭으로 이동한 후, [New pull request] 버튼을 클릭합니다.
    

![pull request](https://user-images.githubusercontent.com/79842129/229303419-73cfc734-3aca-486a-b48f-53e30772defc.png)
<figcaption align = "center">
<b>그림11</b> New pull request 버튼 클릭
</figcaption>
<br></br>
    

### 2. Pull Request를 생성합니다.
    
![create_pr](https://user-images.githubusercontent.com/79842129/229303421-42bc148f-4802-4644-8c52-ad1ba48f0b23.png)
<figcaption align = "center">
<b>그림12</b> Pull Request 생성
</figcaption>
<br></br>

1. 자신의 branch에서 main branch로 pull request를 보냅니다. (방향 설정에 유의하세요!)
2. Pull request 제목, 내용을 작성합니다. (규칙에 맞게 작성해주세요!)
    - 제목: 자신의 이름(Github 아이디) 자기소개

        ex. 에코노(econo) 자기소개

    - 내용: 간단한 한줄 소개

        ex. 안녕하세요! 에코노베이션 25기 에코노입니다.

3. PR에 대한 라벨을 지정합니다. 
    - `자기소개` 라벨과 `자신의 기수`를 나타내는 라벨을 지정해주세요.
4. 마지막으로 [Create pull request] 버튼을 클릭합니다. 

**❗️위 조건을 모두 만족하신 분들에 한해 approve해드리니! 꼭 확인해주세요** 



    

# Review

Pull Request(PR)을 통해 자신이 변경한 내용을 동료에게 전달했으면, 동료는 잘 작업이 되었는지 검토 과정이 필요한데요. 

예를 들어, 저희 TF팀이 함께 이 github자료를 만든다고 해봅시다. 제가 실습 부분을 작성했고 작성한 내용을 도연님, 건형님, 배경님께 전달하기 위해 Pull Request(PR)를 작성하고 이 분들은 제가 작성한 내용이 github 자료에 들어가도 괜찮을지, 잘못된 부분은 없는지 아마 검토하실 것입니다.

우리는 github이 제공하는 리뷰 기능을 이용해 자기소개를 읽으면서 궁금한 점은 질문하고 공감하면서 서로 알아가는 시간을 갖는 것을 목표로 합니다. 

### 1. 리뷰할 사람의 Pull Request를 클릭합니다. 
    

![pr_click](https://user-images.githubusercontent.com/79842129/229303418-917b8ff8-3f6a-4a0b-83fe-8729ea50470f.png)
<figcaption align = "center">
<b>그림13</b> 리뷰할 사람 Pull Request 클릭
</figcaption>
<br></br>

    

### 2. 해당 Pull Request에서 Files changed 탭을 클릭합니다. 
    

![file_changed](https://user-images.githubusercontent.com/79842129/229303417-252baaa7-a644-4218-981c-42de68ee9656.png)
<figcaption align = "center">
<b>그림14</b> Files changed 탭 클릭
</figcaption>
<br></br>

    

### 3. 공감가는 내용이 있는 줄의 [+] 버튼을 클릭하여 자유롭게 의견을 작성한 후 [Start a review] 버튼을 클릭합니다. 
    

![+botton](https://user-images.githubusercontent.com/79842129/229303416-36f6a614-1c2e-44c9-aa8a-a64f3dfd6c2e.png)
<figcaption align = "center">
<b>그림15</b> Start a review 버튼 클릭
</figcaption>
<br></br>
    

### 4. 모든 Review를 작성하셨다면 [Review changes] 버튼을 클릭하고 설정한 후 Review를 제출합니다.

![review](https://user-images.githubusercontent.com/79842129/229303787-5c4dd4c1-6b4f-4810-ace0-5a14480c6d96.png)
<figcaption align = "center">
<b>그림16</b> Review 제출
</figcaption>
<br></br>

**1.** 전제적인 Review 코멘트를 작성합니다.

**2.** **Comment, Approve, Request changes** 설정합니다.

   - **Comment** : approve없이 feedback만 작성

   - **Approve** : PullRequest가 문제 없을 때 선택

   - **Request changes** : 작성된 PullRequest에 수정할 점이 있을 때 선택

    ❗️ branch 방향이 개인 branch → main인지, 라벨을 지정했는지, 타이틀을 작성했는지 등을 확인한 후 만족했을 경우 Approve를 선택합니다.

        

# Merge

<aside>
❗ Merge는 5월 6일 금요일날 진행하실 수 있습니다.

</aside>

6명 이상의 동료로부터 Approve를 받은 사람은 Merge 조건을 충족하여 Merge 받을 수 있습니다. 

### 1. Merge할 동료가 6명 이상에게 **Approve**를 받았는지 확인합니다. 
- Merge할 동료가 6명 이상으로부터 Approve가 채워지지 않았다면 TF팀에게 DM주세요!
    
    ![Untitled](%5B%E1%84%89%E1%85%B5%E1%86%AF%E1%84%89%E1%85%B3%E1%86%B8%5D%20Let's%20git%20it%20started%20%E1%84%89%E1%85%B5%E1%84%8C%E1%85%A1%E1%86%A8%E1%84%92%E1%85%A1%E1%84%80%E1%85%B5%20dd09d6bb3cea4bba988423bebe3583bd/Untitled%2013.png)
    

### 2. [Merge pull request] 버튼을 클릭하여 Merge합니다.
    
    ![Untitled](%5B%E1%84%89%E1%85%B5%E1%86%AF%E1%84%89%E1%85%B3%E1%86%B8%5D%20Let's%20git%20it%20started%20%E1%84%89%E1%85%B5%E1%84%8C%E1%85%A1%E1%86%A8%E1%84%92%E1%85%A1%E1%84%80%E1%85%B5%20dd09d6bb3cea4bba988423bebe3583bd/Untitled%2014.png)
