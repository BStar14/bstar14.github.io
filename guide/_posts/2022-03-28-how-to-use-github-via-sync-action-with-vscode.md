---
layout: post
title: Sync 기능으로 GitHub 사용하기 (with VS Code)
description: >
  Sync 기능을 활용하면 훨씬 간편하게 GitHub 프로젝트를 수행할 수 있습니다.
image: /assets/img/blog/VSC-git-Hub-thumbnail.png
date: 2022-03-28 20:30:00 +0900
last_modified_at: 2022-03-28 20:30:00 +0900
sitemap: false
---

GitHub에서 이루어지는 협업이란 여러 사람이 동시해 수행하는 작업들을 효과적으로 관리하고 적절히 반영해야 하는 일입니다.

원래는 push, fetch, pull, merge 등의 명령어를 통해서 이것을 수행해야 했지만, VS Code Git에서는 이를 조금 더 간소화한 sync라는 기능을 지원합니다.

이번 포스트에서는 sync 기능을 활용하여 GitHub 프로젝트를 수행하는 모습을 보여드리도록 하겠습니다.

---
## Git extensions
---

VS Code에서 Git을 사용할 때에 도움이 되는 확장프로그램이 있습니다.

![](/assets/img/blog/2022-03-28-how-to-use-github-via-sync-action-with-vscode-01.jpg)

좌측 아이콘 중 5번째 extensions 탭에 들어가서 Git을 검색하시면 Git에 관련된 여러가지 확장프로그램들이 나옵니다.

이 중 Git Extension Pack을 인스톨하시면 가장 상단의 Git History, GitLens 등 5개 확장프로그램이 자동으로 설치됩니다.

해당 프로그램이 필수는 아니지만, 앞으로의 게시글에서 틈틈이 활용하는 모습을 보시게 될 것입니다.

---
# Initial condition
---

![](/assets/img/blog/2022-03-28-how-to-use-github-via-sync-action-with-vscode-02.jpg)

이번에는 위 이미지처럼 세팅된 `README.md` 파일을 가지고 작업을 수행해보도록 하겠습니다.

![](/assets/img/blog/2022-03-28-how-to-use-github-via-sync-action-with-vscode-03.jpg)

VS Code로 본 `README.md` 파일입니다.

---
## Sync instead of pushing
---

![](/assets/img/blog/2022-03-28-how-to-use-github-via-sync-action-with-vscode-04.jpg)

Contents 1 에 관한 commit을 수행합니다.

![](/assets/img/blog/2022-03-28-how-to-use-github-via-sync-action-with-vscode-05.jpg)

지난번처럼 좌측 3번째 Source Control 탭을 클릭하고 변경사항을 stage 한 후, commit message를 작성하고, commit을 기록합니다.

![](/assets/img/blog/2022-03-28-how-to-use-github-via-sync-action-with-vscode-06.jpg)

지난번과 달리 Sync Changes라는 버튼이 나타났습니다!

해당 버튼은 GitHub에 이미 존재하는 repository에 컴퓨터가 연결되어 있을 때, 새로운 commit이 생기면 활성화됩니다.

버튼 옆의 1↑ 이라고 표시된 것은 push할 commit이 1개 있다는 의미입니다.

왼쪽 아래에도 보시면 똑같은 sync 아이콘이 있는 것을 확인하실 수 있습니다.

Sync를 수행하면 자동으로 GitHub과 컴퓨터를 동기화하는 작업을 수행합니다.

이 경우에는 push만 수행하면 되겠죠?

![](/assets/img/blog/2022-03-28-how-to-use-github-via-sync-action-with-vscode-07.jpg)

GitHub에 정상적으로 push가 된 것을 확인하실 수 있습니다.

---
## Sync with others
---

위의 예시에서는 sync에서 수행되는 기능이 push밖에 없었는데요, 다른 기능이 수행되는 것도 확인해볼까요?

실제로 GitHub을 이용해 공동작업을 수행할 때에는 앞서 수행된 commit이 다른 사람의 컴퓨터에는 아직 반영이 안 되었을 수 있습니다.

단순히 업데이트를 하지 않아서 그럴 수도 있고, 작업이 동시에 수행되기 때문에 그럴 수도 있겠죠?

![](/assets/img/blog/2022-03-28-how-to-use-github-via-sync-action-with-vscode-08.jpg)

앞서 (author 1)이 수행한 작업이 반영되지 않은 상태에서 (author 2)가 contents 2를 수정했다고 해봅시다.

왼쪽 아래 sync 아이콘에 업데이트 1개가 있다는 표시도 확인해주세요!

![](/assets/img/blog/2022-03-28-how-to-use-github-via-sync-action-with-vscode-09.jpg)

업데이트가 있긴 하지만, (author 2)는 이를 무시하고 변경사항을 commit할 수 있습니다.

![](/assets/img/blog/2022-03-28-how-to-use-github-via-sync-action-with-vscode-10.jpg)

이제 Sync Changes를 수행하려고 하면 이렇게 1↓ 1↑ 표시가 나옵니다.

1개의 commit을 GitHub으로부터 컴퓨터로 pull 해야 하고, 1개의 commit을 컴퓨터에서 GitHub으로 push 해야 한다는 의미입니다.

이제 sync를 수행해볼까요?

![](/assets/img/blog/2022-03-28-how-to-use-github-via-sync-action-with-vscode-11.jpg)

Sync를 수행하면 (author 1)이 수정한 contents 1가 업데이트 되고, (author 2)가 수정한 contents 2도 잘 남게 됩니다.

GitHub repository도 확인해볼까요?

![](/assets/img/blog/2022-03-28-how-to-use-github-via-sync-action-with-vscode-12.jpg)

이미지처럼 contents 1과 contents 2가 모두 업데이트 된 것을 확인할 수 있습니다.

Commit 내역을 확인해보시면 Merge branch 'main' of ~~~ 라는 내용이 표시되는 것이 보이시나요?

이것이 sync에서 자동으로 수행되는 merge 명령어입니다.

![](/assets/img/blog/2022-03-28-how-to-use-github-via-sync-action-with-vscode-13.jpg)

앞에서 확장프로그램을 설치하셨다면 Source Control에서 Git History를 확인하실 수 있습니다.

앞서 진행된 첫번째 commit과 직전에 진행된 두번째 commit이 서로 다른 트리에서 있었고, 이 2개의 트리가 sync에서 수행되는 merge 명령어를 통해 합쳐진 것을 확인하실 수 있습니다.
