# Commit Convention

[1. convention에 대해서](#1-convention에-대해서)

[2. Commit은 왜 필요할까?](#2-commit은-왜-필요할까)

[3. Commit의 구조](#3-commit의-구조)

[4. 대표적인 Commit Convention](#4-대표적인-commit-convention)

[5. 그 외의 Convention들](#5-그-외의-convention들)

## 1. Convention에 대해서


영단어 Convention은 협약, 관례라는 뜻을 가지고 있습니다. 그렇다면 개발에서는 어떤 것을 말할까요? 

보통 commit convention을 정한다고 하는 이 절차는 git으로 commit을 할 때 commit 메세지의 형식을 정하는 과정을 말합니다.

물론 commit만이 convention을 가지는 것은 아니고 pull request와 같은 요청을 보낼 때에도 convention 있다면 더욱 효율적으로 협업이 가능하겠죠?

이러한 convention은 많은 개발자들이 협업을 거치며 효율적이고 효과적인 형식을 만들어 냈습니다. 이 문서의 마지막에서는 이미 만들어져있는 convention들을 소개해드리고 있으니, 각각의 장단점을 파악하며 협업하며 어떤 convention을 선택할지 고민해봅시다.

## 2. Commit은 왜 필요할까?


git은 코드의 버전 관리 시스템입니다. 버전 관리를 하는 이유는 작업 중 **버그가 생긴 부분 이전으로 돌아가야 하는 상황이 생기거나 환경 이전과 같이 다른 환경에서 작업을 해야 하는 상황에서 유용하기 때문**입니다.

이러한 관점에서 commit은 우리가 돌아가야 할 작업이 어디인가를 알려주는 역할을 합니다. 혼자서 작업을 할 때에는 본인이 잘 알아볼 수 있도록 하는 것이 가장 좋겠지만 프로젝트의 크기가 증가하고 다른 사람들과 협업해야하는 경우에는 다른 사람도 알아보기 쉽게끔 작성하는 것이 중요합니다.

## 3. Commit의 구조


commit은 다음과 같은 구조로 이루어져 있습니다.

- **Subject (제목)**
    - commit의 제목을 적습니다. 흔히 commit -m “메세지”로 커밋을 작성하는데, Subject만 작성하는 것입니다.
- **Body (본문)**
    - 해당 commit이 어떤 내용을 어떤 이유에서 변경하거나 추가한 것인지 상세하게 적습니다. 경우에 따라서 예시까지 작성하는 것을 추천하는 경우도 많습니다.
- **Footer (꼬리말)**
    - commit이 어떤 issue를 해결하기 위한 것이라면 issue의 id를 작성합니다.
    - 그렇지 않은 경우에서는 일반적으로 생략 가능합니다.

각 항목은 줄바꿈으로 구분됩니다.

commit이 이러한 구조를 가지고 있음을 인지하고 다음 내용들을 읽어봅시다.

## 4. 대표적인 Commit Convention


가장 널리 사용되는 commit convention은 <b>[AngularJS Git Commit Message Conventions](https://docs.google.com/document/d/1QrDFcIiPjSLDn3EL15IJygNPiHORgU1_OOAqWjiDU5Y/edit)</b>입니다.

이 convention은 다음 세가지 목적을 가지고 만들어졌습니다.

1. CHANGELOG.md를 만들 수 있을 것
2. 중요하지 않은 commit을 구분할 수 있을 것
3. commit history를 보며 더 많은 정보를 얻을 수 있도록 할 것

위와 같은 목적을 달성하기 위해 이 convention은 각각의 commit 구조를 다음과 같은 양식으로 재구성 했습니다.

### Common Rule

- commit 메세지의 모든 라인은 100글자를 넘지 않도록 합니다.
- 이전 commit으로 되돌리는 내용이 있다면 revert: 로 시작하고 body에는 어떤 commit으로 돌아갔는지 명시해야 합니다.
    - ex)
    ```
    revert: 5H46C2
    
    This reverts commit 5H46C2
    
    (issue #1)(optional)
    ```

### Subject

`<type>(<scope>): <subject>`

- `<type>`에는 해당 commit이 어떤 내용을 가지고 있는지 tag를 붙여주는 역할을 합니다. 허용되는 tag는 다음과 같습니다.
    - **feat**
        - feature
        - 기능을 추가할 때 붙이는 tag
    - **fix**
        - bug fix
        - 버그를 수정하거나 의도대로 동작하지 않는 코드를 수정할 때 붙이는 tag
    - **docs**
        - (documentation)
        - 문서를 추가했을 때 붙이는 tag
    - **style**
        - (formatting, missing semi colons, …)
        - 문법적 오류를 고치거나 좀 더 읽기 쉽도록 줄바꿈을 하는 등의 수정이 있을 때 붙이는 tag
    - **refactor**
        - refactorize
        - 기능 단위로 코드를 세분화 하거나 다른 이유로 리팩토링을 했을 때 붙이는 tag
    - **test**
        - (when adding missing tests)
        - 테스트 케이스 등을 추가했을 때 붙이는 tag
    - **chore**
        - (maintain)
        - 유지 보수를 위한 수정이 있을 때 붙이는 tag

- `<scope>`는 commit이 어디에서 일어난 것인지를 알려주는 tag입니다.
    
    예시로는 $location, $browser, $compile, $rootScope, ngHref, ngClick, ngView 과 같은 경로가 가능하며 딱히 위치를 명시할 필요가 없는 commit의 경우에는 *로 대체 가능합니다.
    
- `<subject>`는 해당 commit이 어떤 변화를 가지고 있는지 아주 짧은 문구로 표현합니다.
    - 예를 들어 `<type>`이 feat라면 어떤 기능을 추가했는지 간단하게 명시합니다.
    - 또한 과거형이나 동사를 사용하지 않고 명령형을 사용합니다.
        - ex) changed나 changes가 아닌 change 사용
    - 문장의 끝에 “.”을 사용하지 않습니다.

### Body

- `<body>`에서는 특별한 규칙은 없지만 `<subject>`에서와 마찬가지로 명령형을 사용합니다.
    - 어떤 이유에서 변경하였는지, 어떤 변화가 있었는지를 설명합니다.
    - 각 라인이 100글자를 넘지 않도록 주의합시다!

### Footer

- 중요한 변경사항에 대해서는 모든 사항을 `<footer>`에 기록하고 그외에 이슈로 올라온 버그를 수정했다면 이슈의 번호를 같이 적어줍니다.
    - ex)
        
        BREAKING CHANGE: isolate scope bindings definition has changed and
        the inject option for the directive controller injection was removed.
        close #234
        
        - 여기서 close는 해당 이슈가 close 되었다는 것을 의미합니다.

### Examples
```
feat($homepage): 네비게이션 창 추가

다른 페이지로 더 쉽게 이동할 수 있도록 네비게이션 창 추가

Closes #3
```
```
feat($browser): onUrlChange event (popstate/hashchange/polling)

Added new event to $browser:

- forward popstate event if available
- forward hashchange event if popstate not available
- do polling when neither popstate nor hashchange available
    
Breaks $browser.onHashChange, which was removed (use onUrlChange instead)
```
```
fix($compile): couple of unit tests for IE9

Older IEs serialize html uppercased, but IE9 does not...
Would be better to expect case insensitive, unfortunately jasmine does
not allow to user regexps for throw expectations.

Closes #392
Breaks foo.bar api, foo.baz should be used instead
```
```
feat(directive): ng:disabled, ng:checked, ng:multiple, ng:readonly, ng:selected

New directives for proper binding these attributes in older browsers (IE).

Added coresponding description, live examples and e2e tests.

Closes #351
```
```
style($location): add couple of missing semi colons
```
```
docs(guide): updated fixed docs from Google Docs
    
    Couple of typos fixed:
    
    - indentation
    - batchLogbatchLog -> batchLog
    - start periodic checking
    - missing brace
```
```
feat($compile): simplify isolate scope bindings

Changed the isolate scope binding options to:
- @attr - attribute binding (including interpolation)
- =model - by-directional model binding
- &expr - expression execution binding
This change simplifies the terminology as well as
number of choices available to the developer. It
also supports local name aliasing from the parent.

BREAKING CHANGE: isolate scope bindings definition has changed and
the inject option for the directive controller injection was removed.
```

## 4. 그 외의 Convention들

**AngularJS Git Commit Message Conventions**이외에도 다른 convention들이 존재합니다.

하지만 대부분의 convention들이 **AngularJS Git Commit Message Conventions**를 기반으로 수정을 거친 convention이기 때문에 큰 틀은 변하지 않는다고 생각하시면 될 거 같습니다.

아래에 링크 되어 있는 convention들도 대중적으로 사용되는 convention들입니다.

프로젝트 성격에 맞추어 팀원들과 논의하여 convention을 선택해보시는게 어떨까요?

- [https://udacity.github.io/git-styleguide/](https://udacity.github.io/git-styleguide/)
- [https://www.conventionalcommits.org/en/v1.0.0/](https://www.conventionalcommits.org/en/v1.0.0/)

### Commit Emoji

commit 메세지에 emoji를 사용하는 경우도 정리해놓은 자료가 있었습니다. 

- [https://gitmoji.dev/](https://gitmoji.dev/)

조금 더 활기찬 commit 메세지를 작성해보고 싶은 분들은 참고하셔도 재미있을 것 같아요