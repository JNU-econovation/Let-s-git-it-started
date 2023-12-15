# situation.md

## [First STEP]

1.  JNU-econovation Organization에 TEAM Repository 생성합니다.

## [Second STEP]

1. main branch에 init1.md, [init2.md](http://init2.md) 파일을 생성 후 commit 합니다.
2. main branch 기준에서 develp branch를 생성합니다.
[setting folder](https://github.com/JNU-econovation/Let-s-git-it-started/tree/main/2nd_Let_s_git_it_started(Git_Flow)/setting) 내부 setting1.md, [setting2.md](http://setting2.md) 파일들에 적혀있는 문제들을 init1.md, [init2.md](http://init2.md) 파일에 복사 후 붙여넣기를 합니다. 문제 복사 및 붙여넣기가 끝났다면 init1.md, init2.md 파일들을 각각 answer1.md, [answer2.md](http://answer2.md) 파일명으로 변경 후 commit 합니다.

## [Third STEP]

1. develop branch 기준에서 feature-a, feature-b, feature-c, feature-d 총 4개의 브랜치를 생성합니다.
    1. feature branch의 목적은 ‘기능 개발(문제 풀이)’입니다.
2. feature-a branch에서 [answer1.md](http://answer1.md) 1 ~ 5번 문제를 해결해 주시기 바랍니다. (commit → pr → develop 기준 feature-a branch의 pr을 merge 합시다)
3. feature-b branch에서 [answer1.md](http://answer1.md) 6 ~ 10번 문제를 해결해 주시기 바랍니다. 
    1. 잠깐! 여기서 바로 문제 풀이 후 develop으로 pr을 보내면 Conflict가 발생하겠죠??
    위 상황을 미연에 방지하기 위해 develop branch의 최신 내용을 pull 받아온 후 문제 풀이를 시작합니다! (commit)
4. feature-c branch에서 [answer2.md](http://answer2.md) 1~4번 문제를 해결해 주시기 바랍니다. (commit → pr → develop[HEAD] 기준 feature-c branch의 pr을 merge 합시다)
5. feature-d branch에서 [answer2.md](http://answer1.md) 5 ~ 7번 문제를 해결해 주시기 바랍니다.  (단, 여기서도 pull 받지 않고 문제 풀이를 하면 Conflict가 발생하겠죠??)

## [Resting STEP]

- 자, 여기서 중간 점검 하고 갑시다! 우리는 총 4개의 feature 브랜치를 생성하여 총 17문제를 해결하였습니다. 그렇다면 develop에서는 총 4개의 merge commit이 남았을겁니다. 우리는 문제 풀이를 위해 사용했던 feature branch를 삭제할 거예요. 기능 개발이 완료된 branch는 웬만하면 재사용하지 않는것을 지향합니다. 해당 단계의 마지막 미션은 develop branch에 변경사항을 main branch에 pr을 보낸 후 merge하는 것으로 마무리 하겠습니다!
- 모두 잘 따라왔나요? 다음 단계로 넘어가볼까요!!

## [Final STEP]

- 여기서 잠깐, 회장단이 마지막으로 주는 ❗퀴즈 ❗
회장, 부회장, 총무의 나이 모두 합한 숫자를 [answer2.md](http://answer2.md) 파일 8번 문제의 답으로 작성해 주세요!
단) 주어진 조건에서 해결하시오.
- Hotfix branch를 사용하여 [answer2.md](http://answer2.md) 파일 8번 문제를 해결할 것
- Hotfix branch는 main branch(HEAD)의 기준에서 생성할 것
- 문제를 해결했다면 main으로 pr보낸 후 merge
- 모든 과정을 해결했다면 당신은 이제 깃 마스터!  사용했던 Hotfix branch를 삭제해 주시고, 각 팀의 레포지토리 링크를 ❗JNU-econovation/Let-s-git-it-started [이슈](https://github.com/JNU-econovation/Let-s-git-it-started/issues)에 등록해 주세요~ 고생하셨습니다!
