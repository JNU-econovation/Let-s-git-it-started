# 우리 서로 더 알아가보깃


## 목표

- 프로젝트에서 자주 사용하는 도구 'Git'과 'GitHub'와 친해져보아요!
- 자기를 소개하고 여러 사람들과 함께 이야기를나누며 좀 더 가까워져요!
  <br></br>

## 참여 방법

**4월 12일(금)에 수행해야하는 미션 소개입니다.**

- 자신을 소개하는 글을 작성해서 [Pull Request](#pull-request-보내기)를 올려요! 
  - 문서 제목은 `‘본인이름.md’` 로 저장해주세요
  - pr 제목은 `‘본인이름(깃허브 아이디) - 자기소개’` 형식으로 작성해주세요.
- 혹시 에코노회원분들에게 궁금한 점이 있으신가요? 서로에게 재미난 질문, 궁금한 점을 물어보아요! Issue를 적극적으로 이용해 다양한 질문들을 올려주세요.
- 다른 사람들의 자기소개와 Issue들을 읽으며 댓글과 이모지 등을 활용해 적극적으로 소통해보아요! 📢
- 다른 사람들의 PR을 `review`하신 후 `approve` 해주세요!
- 하시면서 어려움이 생기시다면 언제든지 slack을 적극적으로 활용해주세요! 🔥

<br></br>

**자신을 소개하는 글에는 아래 질문에 대한 대답을 포함해 작성해주세요.**

> - 간단하게 자신에 대해 소개해주세요.
> - 자신을 잘 나타낼 수 있는 키워드를 하나 뽑는다면?
> - 당신이 좋아하는 것은 무엇인가요?
> - 이번 학기에는 어떤 프로젝트/공부를 하시나요?
> - 앞으로 어떤 것을 공부하고 싶으신가요?
> - 마지막으로 하고 싶은 말이 있다면?

- 추가하면 좋을만한 내용💌
  - `에코노베이션 활동을 하면서 해보고 싶은 버킷리스트를 공유해도 좋아요!`
  - `좋아하는 글귀나 가사, 시를 공유해도 좋아요!`
  - `요즘 자주 듣는 노래를 공유해주세요!`

이모지를 활용하시면 더 개성넘치는 글을 작성하실 수 있답니다 :)
<a href="https://www.emojiengine.com/ko/" target="_blank">바로가기</a>

**6명 이상의 동아리원들로부터 `approve`를 받으시고, Issue를 하나 이상 올리시면 확인을 통해 `merge`해드립니다.**

<br></br>

## Pull Request 보내기!

앗! git 명령이 잘 생각나지 않으신다구요? **확인하기**를 눌러보세요✨

1.  명령어 창을 띄우세요.
2.  작업할 폴더(디렉토리)로 이동하여 폴더를 만들어주세요.
   	<details>
	<summary>확인하기</summary>
	<div markdown="1">
	<text> 파일로 들어가기 </text>
	<pre>cd {작업할 디렉토리} </pre>
	<text> 파일 만들기 </text>
	<pre>mkdir [파일이름]</pre>
	<text> 내부 파일 확인 </text>
	<pre>ls</pre>
	</div>
	</details>
3. 작업할 폴더에서 git init 해주세요.
4. git 사용이 처음인 경우 이름과 이메일을 설정해주세요.
   	<details>
	<summary>확인하기</summary>
	<div markdown="1">
	<text> 이름, 이메일 설정하기 </text>
	<pre> git config --global user.name "[본인 이름]"
	git config --global user.email "[본인 이메일]"
	git config --global --list </pre>
	</div>
	</details>
5. 다음의 저장소를 본인 repository로 fork 해주세요.
6. 자신의 local에 원격 저장소 등록하기
   	<details>
	<summary>확인하기</summary>
	<div markdown="1">
	<text> 원격 저장소 추가하기 </text>
	<pre> git remote add [저장소 이름] [저장소 주소] 
	git remote -v </pre>
	</div>
	</details>
7. 자신의 local에 원격 저장소 내역 가져오기
      	<details>
	<summary>확인하기</summary>
	<div markdown="1">
	<text> 원격 브랜치에서 pull 해오기 </text>
	<pre> git pull [저장소 이름] [가져올 브랜치] </pre>
	</div>
	</details>

8. 준비해 온 자기소개 글 수정하기
   	<details>
	<summary>확인하기</summary>
	<div markdown="1">
	<text> profile.md 파일을 복사하기 </text>
	<pre> cd [폴더명]/
	ls
	cp [복사할 파일] [복사될 파일]
	ls</pre>
	</div>
	</details>
9. local 저장소의 변경사항을 저장하고 원격 저장소에 보내기
   	<details>
	<summary>확인하기</summary>
	<div markdown="1">
	<text> add 하기 </text>
	<pre>git add [파일명]</pre>
	<text> commit 하기 </text>
	<pre>git commit -m "메시지 내용"</pre>
	<text> 저장 상태 보기 </text>
	<pre>git status</pre>
	<text> 원격 저장소에 push 하기 </text>
	<pre>git push [저장소 이름] [브랜치]</pre>
	</div>
	</details>
 10. GitHub에서 본인의 repository에서 원래의 repository의 2024-1 브랜치로 Pull Request를 날립니다.
   - 제목은 '자신의 이름(자신의 GitHub 아이디) - 자기 소개'로 해주세요.
     ex) 에코노(econo) - 자기소개
   - Pull Request 내용은 한줄로 간단하게 자신을 소개하는 내용을 담아주세요.
     ex) 안녕하세요! 에코노베이션 그 자체! 에코노입니다.
 11. PR문서에 `자기 소개`와 `기수` label을 달아주세요!
