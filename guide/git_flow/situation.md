# Situation

### [step 1]
1. JNU-econovation Organization에 TEAM Repository 생성합니다.

### [step 2]
1. main branch에 init 폴더에 존재하는 init1.md, init2.md 파일을 commit합니다.
2. main branch에서 develop branch을 생성합니다.
    - develop branch에 setting 폴더에 존재하는 setting1.md, setting2.md파일을 copy and paste하여 commit합니다.
    - 1번 develop branch의 목적은 ‘환경 세팅’입니다.
    - 환경 세팅이라 함은, 버전, 라이브러리, 프레임워크 셋팅 등이 있겠습니다만, 우리는 md파일로 실습하므로, 문제를 복붙하는 것입니다. (교수님이 1번부터 25번 문제 다 있는지 확인해라~ 하는거랑 비슷함)

### [step 3]
1. 2번 develop branch에서는 두 개의 feature branch (next feature, future feature) 를 생성합니다. (commit)
    - feature branch의 목적은 ‘기능 개발’입니다. 여러분이 그냥 main 이나 develop에서 기능개발을 하다가 실수로, 혹은 샷건을 치다가, 아니면 고양이가 키를 잘못 눌러서 전체 코드에 문제가 생기면 대참사입니다. 하지만 기능을 나눠 개발하면 한 가지 기능만 다시 작성하면 되겠죠? (고양이를 안데려오면 될 일입니다.)
2. 1번 next feature branch 에서는 5문제를 해결합니다. (commit)
3. 2번 next feature branch 에서는 5문제를 해결합니다. (commit)
4. 2번 next feature branch 에서 3번 develop branch로 pull request를 보냅시다. (commit)
    - 그럼 여기선 총 10 문제가 3번 develop branch 에 있겠죠?

### [step 4]
1. 1번 future feature branch 에서는 3문제를 해결합니다. (commit)
2. 2번 future feature branch 에서는 4문제를 해결합니다. (commit)
3. 2번 future feature branch 에서 4번 develop branch로 pull request를 보냅시다. (commit)
    - 그럼 여기선 총 17문제가 4번 develop branch 에 있겠죠?
4. 4번 develop branch에서 1번 release branch로 pull request를 보냅시다. (commit)
    - release branch의 목적은 개발된 내용을 배포하기 위해 준비하는 브랜치 입니다. 라고 하면 이해 못하실 거 알고 있습니다. (저도 못했음, 지금도 모름)
    - 버전, 이름, 변수 등의 소소한 데이터를 수정하거나 (변수를 님들 맘대로 해놓으면, 다른 사람들이 코드보고 이해를 못하겠죠?), 배포 전 사소한 버그를 수정하기 위해 사용하는 브랜치입니다.
5. 1번 release branch에서 2번 main branch로 pull request를 보냅시다. (commit)
- 이야 끝났따!!!!!!!!!!!!! 일 줄 알았지만 아닙니다.
    
    저희는 총 18문제를 드렸는데요?
    
    1문제가 없죠?
    
    왜 그럴까요? 한 번 알아봅시다.
    
- 이렇게 갑작스럽게 이미 배포된 버전에 문제가 발생했을 경우엔 Hotfix 브랜치를 사용합니다.
    - 왜 develop 안가고 여기서 하냐구요? develop 브랜치 하나하나 다 들어가서 revert, reset 쓰면서 수정하기는 어렵기 때문이에요.
    - 만들라면 만들겠지만 굉장히 불필요한 리소스가 많이 들어갑니다.
    - 버그 한개의 수정만을 위한 Hotfix 브랜치를 생성하는 순간, 다음 버전의 배포(업그레이드라던지?)를 위해 개발하던 작업 내용에 방해를 주지 않으므로, 버그 전담팀에서는 Hotfix브랜치에서만 일하고, 나머지 브랜치는 각 팀에서 병렬적으로 일처리가 가능하게 해줍니다.

### [step 5]
1. 2번 main branch에서 1번 hotfix 브랜치를 생성해주고 버그(나머지 문제 하나 남은거)를 해결해줍시다. (commit)
2. 그럼 이제 다 해결된 1번 hotfix 브랜치에서 3번 main branch로 pull request 를 보냅시다. (commit)
- 다 해결되었죠? 그럼 이제 git log graph를 살펴봅시다. 상당히 지저분한 것을 볼 수 있습니다. 따라서 이제 사용하지 않는 브랜치를 삭제하도록 하겠습니다.

    삭제 명령어는 다음과 같습니다.
    
    git branch -d {브랜치명}
    
3. develop, main branch를 제외한 branch들은 삭제해줍시다.

### [step 6]
위 5단계를 모두 거친 후 각 팀의 레포지토리 링크를 [이슈로 등록](https://github.com/JNU-econovation/Let-s-git-it-started/issues) 해주세요~