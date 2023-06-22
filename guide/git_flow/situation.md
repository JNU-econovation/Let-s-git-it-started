# Situation
여러분 팀은 특정 소프트웨어 개발에 있어 버전 관리를 위해 Git 도입하기로 하였습니다. 

개발을 진행하며 main 브랜치의 무결성을 위해 Git flow를 지향하고, GitHub를 사용하여 개발하기로 했습니다.

- main 브랜치의 무결성이란?

    - main에서 오류가 발생하면 큰 문제로 이어질 수 있습니다. 이를 해결하기 위해서 main 브랜치에 merge를 하기 전 다른 브랜치에서 충분히 테스트와 검사를 한 후에 merge하는 전략을 사용해야 합니다.

[git_flow_theory](git_flow_theory.md)를 참고하며 진행해봅시다.


## [step 1]

1. 팀별로 머지요정이 보내준 init.md 파일을 받습니다.

    (git_flow에서도 파일을 받을 수 있습니다.)

2. JNU-econovation Organization에 TEAM Repository 생성합니다.

3. 팀만의 commit convention과 pr명을 만듭니다.
    
    ([이전에 사용한 commit convention](../exercise.md/#4-git-commit))

## [step 2]

1. TEAM Repository에 git flow에 필요한 branch들을 생성합니다.

2. main branch에 init.md 파일을 push합니다.

## [step 3]

1. [git_flow_theory](git_flow_theory.md)를 참고하며 각 스텝마다 md파일을 수정하며 push, pull 합니다.

2. md파일이 잘 수정되고 있는지 알고 싶다면 solution 폴더에서 각 branch별로 노드의 답을 확인할 수 있습니다.

## [step 4]

1. step 3를 모두 진행한 후에 main 브랜치의 마지막에 있는 md파일이 모든 이슈를 해결했는지 확인합니다.

2. 해결되었다면 JNU-ecnovation/Let-s-git-it-started에 issues를 생성 후 TEAM Repository link 첨부합니다.

## [step 5]

다른 팀들이 진행한 repository의 commit log를 확인하고 대댓글을 달아봅시다.


