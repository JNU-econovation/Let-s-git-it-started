이번엔 브랜치 전략 중 하나인 git-flow에 대해서 알아보겠습니다.

### [ 브랜치 전략을 설정하는 이유 ]
우선 브랜치 전략을 세우는 이유가 무엇일까요?

바로 여러 개발자가 하나의 저장소를 사용하는 환경에서 저장소를 효과적으로 활용하기 위해서입니다.

브랜치 전략이 없다면 어떤 브랜치에 push 해야 하는지, 또한 어떤 브랜치에서 pull을 해와서 개발을 시작해야 하는지 등부터 많은 혼란을 야기할 것입니다.

가장 널리 사용되는 브랜치 전략은 git-flow, github-flow 전략이 있습니다.

이번 시간을 통해서 여러분이 브랜치 전략에 대해서 알아보시고, 팀끼리의 브랜치 전략을 세울 수 있는 시간이 되면 좋겠습니다.

오늘 알려드린 git-flow 전략이 팀과는 어울리지 않는 브랜치 전략일 수도 있습니다. git-flow 전략이 무조건 따라야 하는 좋은 전략은 아니니 팀 상황을 고려해서 알맞은 브랜치 전략을 세우는 데 참고하시면 좋겠습니다.

# git-flow
크게 5개의 브랜치를 운영하며 관리를 한다.
* 메인 브랜치 : master, develop
* 보조 브랜치 : feature, release, hotfix

<img width="636" alt="image" src="https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/c62c07ee-9a42-43b5-b0eb-58e388849c78">

## 메인 브랜치들의 특징
---
* master : 배포 가능한 상태만을 관리하는 브랜치
* develop : 다음에 배포할 것을 개발하는 브랜치

위 2개의 브랜치는 항상 남아있다.

<img width="315" alt="image" src="https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/e8b33af9-dc61-4987-bfee-b66f64885401">

develop 브랜치는 처음 master 브랜치에서 분기하는 것으로 시작하며 <b>다음 버전 구현이 완료되어 배포를 하고 싶을 때  master로 다시 합치는 방식 </b>으로 운영된다.


## 보조 브랜치의 특징
* feature : 기능 구현을 위해 사용하는 브랜치
* release : 개발된 내용을 배포하기 위해 준비하는 브랜치
* hotfix : 버그의 빠른 수정을 위해 사용하는 브랜치

보조 브랜치들은 메인 브랜치와는 달리 사용을 마치면 브랜치를 삭제한다.

### [ feature 브랜치 ]
feature 브랜치는 기능의 구현을 담당한다.

브랜치명은 팀 컨벤션을 따르면 된다.
ex) feature/logi feature/#1(issue 번호)
<img width="517" alt="image" src="https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/8e6bfdb7-8f20-44aa-9d8c-4d7c8e121189">

feature 브랜치는 develop 브랜치에서 생성되며, 기능 구현이 완료된 이후에 develop 브랜치로  merge 된다.

또한 merge된 이후에는 해당 feature 브랜치는 삭제된다.

### [ release 브랜치 ]
release 브랜치는 다음 버전 출시를 위한 기능 개발을 한다.

release 브랜치가 배포를 위한 준비를 하는 동안 develop 브랜치는 기능 개발을 지속할 수 있다는 장점이 있다.

release 브랜치 또한 팀 컨벤션을 따르면 되지만

주로 release-1.2, release/1.2처럼 이름 짓는 게 일반적인 관례이다.

<img width="516" alt="image" src="https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/f66f5f73-16f4-4451-a836-b9af22ef1a51">

develop 브랜치에서 배포할 수 있는 수준의 기능이 모이면 release 브랜치를 분기한다.

release 브랜치에서는 <b>기능 개발은 하지 않고</b> 버그 수정, 문서 추가 등 <u>릴리즈와 관련된 작업</u>을 수행한다.

만약, release 브랜치에서 배포 준비가 완료되면
master 브랜치와 develop 브랜치에 merge 한다.

### [ hotfix 브랜치 ]
배포한 버전에서 긴급하게 수정을 해야 할 필요가 있을 경우, master 브랜치에서 분기하는 브랜치이다.

hotfix 브랜치 또한 팀 컨벤션을 따르면 되지만

주로 hotfix-1.2.1 이름 짓는 게 일반적인 관례이다.(master 브랜치의 tag가 1.2였을 경우)

<img width="494" alt="image" src="https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/31bbfddf-94bd-4718-8faa-fb968a6bd36f">

이미 출시된 버전에서 수정사항이 생겼을 경우 master 브랜치에서 분기하여 hotfix 브랜치를 생성한다.

이후 문제가 되는 부분을 수정하고

다시 master 브랜치에 merge하여 재배포한다.(이때 새로운 버전 이름으로 태그를 매긴다.)

또한 hotfix 브랜치에서의 변경 사항은 develop 브랜치에도 merge한다.