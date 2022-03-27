---
layout: post
title: GitHub 첫 번째 commit하기 (with VS Code)
description: >
  Git에 첫 번째 commit을 등록하고 GitHub repository로 push해봅시다.
image: /assets/img/blog/VSC-git-Hub-thumbnail.png
date: 2022-03-27 19:20:00 +0900
last_modified_at: 2022-03-27 19:20:00 +0900
sitemap: false
---

컴퓨터와 GitHub을 잘 연결하셨다면 이제 GitHub에 첫 번째 파일을 올려보도록 합시다.

---
## Git initial setting
---

파일을 올리기에 앞서 Git을 처음 사용하신다면 Git에 계정정보를 먼저 등록하셔야 합니다.

![](/assets/img/blog/2022-03-27-how-to-make-the-first-commit-with-vscode-01.jpg)

VS Code 상단의 View(보기) - Terminal(터미널) 메뉴를 선택하시거나, 단축키 `` Ctrl+` `` 을 입력해 터미널을 열어줍니다.

![](/assets/img/blog/2022-03-27-how-to-make-the-first-commit-with-vscode-02.jpg)

Git에 유저 이름과 이메일을 등록해줍니다.

명령어는 아래와 같습니다.

~~~
git config --global user.name "Your Name"
~~~

~~~
git config --global user.email "you@example.com"
~~~

username은 일반적으로 실명을 입력하는 경우가 많은 것 같습니다.

---
## Commit
---

Commit은 Git에 파일 변경사항을 기록하는 것입니다.

이번에는 GitHub repository 첫 페이지에 나타나는 `README.md` 파일을 만드는 것으로 첫 번째 commit을 작성해보도록 하겠습니다.

![](/assets/img/blog/2022-03-27-how-to-make-the-first-commit-with-vscode-03.jpg)

VS Code 좌측 상단 메뉴에서 New File 아이콘을 클릭해 새로운 파일을 생성합니다.

파일 이름은 `README.md`로 직접 입력해줍니다.

![](/assets/img/blog/2022-03-27-how-to-make-the-first-commit-with-vscode-04.jpg)

우측 화면에 `README.md` 파일이 자동으로 열립니다.

`README.md` 파일과 같은 markdown 파일 형식은 비교적 간편하게 글을 작성할 수 있는 파일 형식입니다. (이 블로그 글도 markdown 형식으로 작성하고 있습니다.)

`README.md` 파일에 제목으로 이 repository의 이름인 example을 입력하고 `Ctrl+S`를 눌러 저장합니다.

> 참고! # 뒤에 나오는 텍스트는 Heading 1 서식이 자동으로 적용됩니다.

![](/assets/img/blog/2022-03-27-how-to-make-the-first-commit-with-vscode-05.jpg)

이제 좌측을 보시면 3번째 아이콘에 '1' 이라는 알림 배지가 표시되는 것을 확인하실 수 있습니다.

해당 탭은 Source Control 탭으로 VS Code에서 Git에 관련된 거의 모든 기능은 여기에서 찾아볼 수 있습니다.

Source Control 탭으로 들어가시면 방금 작성한 `README.md` 파일이 변경내역에 올라와있는 것을 확인할 수 있습니다.

해당 파일에 마우스를 올리면 해당 변경내역을 stage할 수 있는 + 아이콘이 나타납니다.

![](/assets/img/blog/2022-03-27-how-to-make-the-first-commit-with-vscode-06.jpg)

Stage된 변경내역을 요약하는 commit message를 작성합니다.

다음으로 Source Control의 체크 버튼을 누르시면 commit을 등록할 수 있습니다.

---
## Push
---

Commit을 통해 등록된 변경내역은 push를 통해 GitHub repository에 올릴 수 있습니다.

![](/assets/img/blog/2022-03-27-how-to-make-the-first-commit-with-vscode-07.jpg)

Source Control의 ... 아이콘을 클릭하고 나타난 메뉴에서 push를 클릭합니다.

![](/assets/img/blog/2022-03-27-how-to-make-the-first-commit-with-vscode-08.jpg){:width="400"}

처음 push를 할 때에는 위와 같이 GitHub에 로그인하라는 창이 나타납니다.

Sign in with your browser 버튼을 누르고 나타나는 창에서 GitHub에 로그인해주세요.

![](/assets/img/blog/2022-03-27-how-to-make-the-first-commit-with-vscode-09.jpg){:width="600"}

GitHub에 한 번 로그인 하고나면 이후에는 로그인을 다시 요구하지 않습니다.

![](/assets/img/blog/2022-03-27-how-to-make-the-first-commit-with-vscode-10.jpg)

Push가 완료되고 나서 example repository를 새로고침해보면 위와 같이 `README.md` 파일이 정상적으로 게시된 것을 확인하실 수 있습니다.
