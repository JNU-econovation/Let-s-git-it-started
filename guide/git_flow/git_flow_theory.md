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
* 메인 브랜치 : main, develop
* 보조 브랜치 : feature, release, hotfix

![git-flow 가이드 흐름도](https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/1bb77009-87da-46eb-9527-627763964f46)



## 메인 브랜치들의 종류
---
* main : 배포 가능한 상태만을 관리하는 브랜치
* develop : 다음에 배포할 것을 개발하는 브랜치

위 2개의 브랜치는 항상 남아있습니다.

![사진1](https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/08f0472c-a562-4463-9260-87bd30f63ea1)

develop 브랜치는 처음 master 브랜치에서 분기하는 것으로 시작하며 <b>다음 버전 구현이 완료되어 배포를 하고 싶을 때  master로 다시 합치는 방식 </b>으로 운영됩니다.


## 보조 브랜치의 종류
* [feature](#feature-브랜치) : 기능 구현을 위해 사용하는 브랜치
* [release](#release-브랜치) : 개발된 내용을 배포하기 위해 준비하는 브랜치
* [hotfix](#hotfix-브랜치) : 버그의 빠른 수정을 위해 사용하는 브랜치

보조 브랜치들은 메인 브랜치와는 달리 사용을 마치면 브랜치를 삭제합니다.

### [ #feature 브랜치 ]
feature 브랜치는 기능의 구현을 담당합니다.

브랜치명은 팀 컨벤션을 따르면 됩니다.
ex) feature/logi feature/#1(issue 번호)
![사진4](https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/fa6308d8-b1bb-4eb8-86e3-98d8ba161f29)


feature 브랜치는 develop 브랜치에서 생성되며, 기능 구현이 완료된 이후에 develop 브랜치로  merge 됩니다.

또한 merge된 이후에는 해당 feature 브랜치는 삭제됩니다.

### [ #release 브랜치 ]
release 브랜치는 다음 버전 출시를 위한 기능 개발을 합니다.

release 브랜치가 배포를 위한 준비를 하는 동안 develop 브랜치는 기능 개발을 지속할 수 있다는 장점이 있습니다.

release 브랜치 또한 팀 컨벤션을 따르면 되지만

주로 release-1.2, release/1.2처럼 이름 짓는 게 일반적인 관례입니다.

![사진2](https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/cc543ac8-3895-4c45-9e63-cb1fc548594a)


develop 브랜치에서 배포할 수 있는 수준의 기능이 모이면 release 브랜치를 분기합니다.


release 브랜치에서는 <b>기능 개발은 하지 않고</b> 버그 수정, 문서 추가 등 <u>릴리즈와 관련된 작업</u>을 수행합니다.


만약, release 브랜치에서 배포 준비가 완료되면
master 브랜치와 develop 브랜치에 merge 합니다.


### [ #hotfix 브랜치 ]
배포한 버전에서 긴급하게 수정을 해야 할 필요가 있을 경우, master 브랜치에서 분기하는 브랜치입니다.


hotfix 브랜치 또한 팀 컨벤션을 따르면 되지만

주로 hotfix-1.2.1 이름 짓는 게 일반적인 관례입니다.(master 브랜치의 tag가 1.2였을 경우)

![사진3](https://github.com/JNU-econovation/Let-s-git-it-started/assets/88534959/45be46c3-a3d8-4a19-9c3f-c9c72ce23067)

이미 출시된 버전에서 수정사항이 생겼을 경우 master 브랜치에서 분기하여 hotfix 브랜치를 생성합니다.


이후 문제가 되는 부분을 수정하고

다시 master 브랜치에 merge하여 재배포합니다. (이때 새로운 버전 이름으로 태그를 매깁니다.)


또한 hotfix 브랜치에서의 변경 사항은 develop 브랜치에도 merge합니다.
