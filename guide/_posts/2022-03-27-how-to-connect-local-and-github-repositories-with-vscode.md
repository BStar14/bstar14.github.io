---
layout: post
title: 컴퓨터와 GitHub 연결하기 (with VS Code)
description: >
  내 컴퓨터의 폴더와 GitHub repository를 Visual Studio Code를 이용해 연결해봅시다. Clone을 이용하면 복잡한 절차 없이 빠르게 컴퓨터와 GitHub을 연결할 수 있습니다.
image: /assets/img/blog/VSC-git-Hub-thumbnail.png
date: 2022-03-27 17:20:00 +0900
last_modified_at: 2022-03-27 17:20:00 +0900
sitemap: false
---

[GitHub 회원가입](2022-02-22-introducntion-to-github), [Visual Studio Code 설치](2022-03-26-how-to-install-visual-studio-code), [Git 설치](2022-03-27-how-to-install-git)까지 완료하셨다면 드디어 Git, GitHub을 사용하기 위한 준비가 모두 끝났습니다!

이제 본격적으로 GitHub 이용을 시작해보려고 합니다.

예시로 사용할 repository는 지난번에 만든 "example" repository입니다. Repository를 만드는 방법은 [GitHub repository 생성하기](2022-02-28-how-to-create-github-repository) 포스트를 참고해주세요!

![](/assets/img/blog/2022-03-27-how-to-connect-local-and-github-repositories-with-vscode-01.jpg)

연결하고 싶은 GitHub repository의 주소를 복사해둡니다.

아무것도 없는 repository에는 위 이미지와 같이 setup 안내 페이지가 나오는데요, 페이지 아래의 nerdy한 커맨드라인은 가볍게 무시해주시고 위에 표시되는 페이지 주소만 그대로 복사해주세요.

주소 형식은 예시처럼 `.git` 이 들어간 주소여도 좋고,

~~~
https://github.com/UserID/repository.git
~~~

`.git` 부분 없이 그냥 인터넷 주소를 가져가셔도 괜찮습니다.

~~~
https://github.com/UserID/repository
~~~

---
## Clone repository
---

컴퓨터와 GitHub을 연결하는 몇 가지 방법이 있지만, 가장 단순하고 확실한 방법은 repository를 먼저 만들고 clone을 하는 방법입니다.

이 방법을 이용하면 아무것도 없는 repository부터 파일이 꽉꽉 들어찬 repository까지 무엇이든 곧바로 내 컴퓨터로 연결할 수 있습니다.

앞에서 정한 GitHub repository를 다운로드 받기 위해 컴퓨터에 적절한 폴더를 하나 만듭니다.

![](/assets/img/blog/2022-03-27-how-to-connect-local-and-github-repositories-with-vscode-02.jpg)

저는 내 문서에 GitHub 폴더를 하나 만들어봤습니다. 해당 폴더에서 옵션 메뉴를 열어보시면 "Open with Code" 또는 "Code(으)로 열기" action이 있는 것을 찾을 수 있을 것입니다.

만약 VS Code를 설치했는데 해당 action이 나오지 않는다면 VS Code 설치 시 옵션을 선택하지 않으셨을 수 있습니다. [Visual Studio Code 설치하기](2022-03-26-how-to-install-visual-studio-code) 포스트를 다시 확인해보세요.

문제없이 action을 찾으셨다면 그대로 클릭해주시면 됩니다!

![](/assets/img/blog/2022-03-27-how-to-connect-local-and-github-repositories-with-vscode-03.jpg)

정상적으로 VS Code를 실행하셨다면 위와 같은 화면을 보게 될 것입니다.

기본적으로 실행되는 Get Started 페이지에서 곧바로 `Clone Git Repository...` 메뉴를 찾을 수 있습니다.

![](/assets/img/blog/2022-03-27-how-to-connect-local-and-github-repositories-with-vscode-04.jpg)

URL을 입력할 수 있는 박스가 뜨면 아까 복사해뒀던 URL을 붙여넣기해줍니다.

Clone from URL을 선택해주세요!

![](/assets/img/blog/2022-03-27-how-to-connect-local-and-github-repositories-with-vscode-05.jpg)

해당 repository를 어느 폴더로 다운로드 받을지 선택하는 대화창이 뜹니다.

아까 만들어두었던 GitHub 폴더를 찾아서 선택해주세요.

![](/assets/img/blog/2022-03-27-how-to-connect-local-and-github-repositories-with-vscode-06.jpg)

Clone이 완료되면 GitHub 폴더 아래에 example 폴더가 생성됩니다.

해당 폴더는 GitHub의 example repository와 동기화되는 폴더라고 생각하시면 됩니다.

아래 메세지에서 Open 버튼을 클릭해볼까요?

![](/assets/img/blog/2022-03-27-how-to-connect-local-and-github-repositories-with-vscode-07.jpg)

이제 VS Code의 base 위치가 example 폴더로 변경되었습니다.

이 폴더에서 이제 편집되는 파일들은 Git을 이용해 변경 이력을 추적, 관리할 수 있으며, GitHub에 동기화할 수 있게 됩니다.

![](/assets/img/blog/2022-03-27-how-to-connect-local-and-github-repositories-with-vscode-08.jpg)

Windows 탐색기에서 GitHub 폴더를 열어보면 example repository가 다운로드 된 것을 확인하실 수 있습니다.

![](/assets/img/blog/2022-03-27-how-to-connect-local-and-github-repositories-with-vscode-09.jpg)

example repository 안에는 .git 이라는 폴더가 만들어져 있습니다.

Git 프로그램은 해당 폴더 안에 repository 내 파일들의 변경 이력을 저장하게 됩니다.
