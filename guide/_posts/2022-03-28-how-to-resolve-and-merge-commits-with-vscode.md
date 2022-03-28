---
layout: post
title: GitHub commits resolve & merge하기 (with VS Code)
description: >
  Merge 도중 충돌이 발생하는 경우에는 Git이 해당 부분을 resolve 해달라는 요청을 띄우게 됩니다.
image: /assets/img/blog/VSC-git-Hub-thumbnail.png
date: 2022-03-28 21:40:00 +0900
last_modified_at: 2022-03-28 21:40:00 +0900
sitemap: false
---

앞에서 우리는 VS Code에서 commit을 하고, push, pull, merge 등이 자동으로 수행되는 sync 기능을 통해 GitHub과 동기화 작업을 수행했습니다.

하지만 상황에 따라 Git이 자동으로 파일의 변경사항을 적용하기가 어려운 경우가 있습니다.

서로 다른 작업트리에서 진행된 commit을 merge할 때에 이런 상황이 발생하면 Git은 해당하는 부분을 보여주며 문제를 "resolve" 해달라는 요청을 띄우게 됩니다.

이번 포스트에서는 이러한 예외적 상황을 처리하는 법에 대해 다뤄보도록 하겠습니다.

---
# Initial condition
---

![](/assets/img/blog/2022-03-28-how-to-resolve-and-merge-commits-with-vscode-01.jpg)

이번에도 `README.md` 파일을 가지고 작업을 수행합니다. 처음 상태는 위와 같습니다.

![](/assets/img/blog/2022-03-28-how-to-resolve-and-merge-commits-with-vscode-02.jpg)

VS Code로 본 `README.md` 파일입니다.

---
## First commit
---

첫 번째 commit을 수행해봅시다.

다른 변경사항이 없으므로 이전과 같은 방법으로 자연스럽게 처리됩니다.

![](/assets/img/blog/2022-03-28-how-to-resolve-and-merge-commits-with-vscode-03.jpg)

수정하고, 저장하고, Source Control에 가서, stage합니다.

![](/assets/img/blog/2022-03-28-how-to-resolve-and-merge-commits-with-vscode-04.jpg)

메세지를 작성하고, commit합니다.

![](/assets/img/blog/2022-03-28-how-to-resolve-and-merge-commits-with-vscode-05.jpg)

Sync를 수행합니다.

![](/assets/img/blog/2022-03-28-how-to-resolve-and-merge-commits-with-vscode-06.jpg)

첫 번째 commit이 반영되었습니다.

---
## Second commit
---

두 번째 commit을 수행해봅시다.

앞의 변경사항이 있지만, 이를 무시하고 commit을 작성합니다.

![](/assets/img/blog/2022-03-28-how-to-resolve-and-merge-commits-with-vscode-07.jpg)

앞의 1번 commit과 같은 부분에 내용을 작성한 것을 확인해주세요.

이 commit은 1번 commit과 내용이 겹칠 수도 있고, 그냥 같은 위치에 작성된 다른 내용일 수도 있습니다.

어찌됐든 이 commit을 작성할 때에는 1번 commit을 반영하지 않은 상황입니다.

![](/assets/img/blog/2022-03-28-how-to-resolve-and-merge-commits-with-vscode-08.jpg)

일단은 계속해서 commit을 수행해봅시다.

![](/assets/img/blog/2022-03-28-how-to-resolve-and-merge-commits-with-vscode-09.jpg)

1개의 pull, 1개의 push 작업이 진행된다고 합니다.

과연 어떻게 될까요?

---
## Resolve conflicts
---

![](/assets/img/blog/2022-03-28-how-to-resolve-and-merge-commits-with-vscode-10.jpg)

문제가 생겼습니다!

first commit과 second commit이 같은 부분에 수정을 가하고 있기 때문에 conflict이 발생하게 되고, 이 문제를 resolve 해달라는 요청이 뜨게 됩니다.

이 2개의 commit은 어느 하나만 반영해야 할 수도 있고, 둘 다 반영해야 하는 것일 수도 있습니다.

만약 지난번에 확장프로그램을 설치하셨으면 GitLens의 기능으로 위와 같은 선택지가 곧바로 보이게 됩니다.

이번 예시에서는 commit 2개가 모두 반영되어야 하는 상황이라고 해봅시다.

![](/assets/img/blog/2022-03-28-how-to-resolve-and-merge-commits-with-vscode-11.jpg)

Accept Both Changes를 선택하게 되면 commit이 이루어진 순서 그대로 변경사항이 적용되게 됩니다.

6번 라인 아래에 first commit이 먼저 추가되었고 second commit이 그 다음에 똑같이 6번 라인 아래에 추가되었으므로 second commit이 위, first commit이 아래에 자리잡게 됩니다.

![](/assets/img/blog/2022-03-28-how-to-resolve-and-merge-commits-with-vscode-12.jpg)

Merge를 수행하는 중에는 이러한 변경사항을 조정하는 것도 가능합니다.

제가 처음에 의도했던 것은 first commit 아래에 second commit이 오도록 하는 것입니다.

파일을 적절히 수정하고 (이제 first commit과 second commit이 잘 정리되었습니다)

저장하고, 변경사항을 stage합니다.

![](/assets/img/blog/2022-03-28-how-to-resolve-and-merge-commits-with-vscode-13.jpg)

Commit message에 경고가 나오지만 가볍게 무시해주시고 commit을 수행합니다.

![](/assets/img/blog/2022-03-28-how-to-resolve-and-merge-commits-with-vscode-14.jpg)

이제 sync를 통해 2개의 push가 이루어진다고 나오는데요,

1개는 second commit이고, 1개는 merge 작업에 해당합니다.

Sync를 수행해볼까요?

![](/assets/img/blog/2022-03-28-how-to-resolve-and-merge-commits-with-vscode-15.jpg)

이제 의도한대로 first commit과 second commit이 모두 반영되었습니다!

![](/assets/img/blog/2022-03-28-how-to-resolve-and-merge-commits-with-vscode-16.jpg)

Git History를 확인하시면 이렇게 나옵니다. (마지막 4개 commit)
