---
layout: post
title: Git 시작하기
description: >
  Git은 컴퓨터 파일의 변경사항을 추적하고 여러 명의 사용자들 간에 해당 파일들의 작업을 조율하기 위한 분산 버전 관리 시스템입니다. (위키백과)
image: /assets/img/blog/VSC-git-Hub-thumbnail.png
date: 2022-03-27 14:10:00 +0900
last_modified_at: 2022-03-27 15:00:00 +0900
sitemap: false
---

제가 Git을 처음 사용할 때 이 프로그램은 그저 GitHub에 딸린 어렵고 거추장스러운 프로그램에 불과했습니다.

VS Code같은 GUI를 통해 Git을 다루는 방법도 찾지 못했어서, 터미널 명령어로만 다뤄야 한다는 부담감도 상당했고요.

아마 Git을 제대로 사용하기 시작한 건 이 블로그를 만들면서부터였던 것 같은데, 이 때 VS Code에 Git을 연동하여 사용할 수 있다는 것을 처음 알았습니다.

지금에와서는 Git이 블로깅 뿐만 아니라, 코딩 작업에서도 없어서는 안 되는 프로그램이구나 하는 것을 뼈저리게 느끼고 있죠.

이번 포스트에서는 그래서 Git이라는 프로그램에 대한 개인적인 의견을 조금 써보려 합니다.

---
## Git Features
---

Git의 장점을 한 마디로 표현하면, 파일을 덮어쓰는 대신에 '변경 내용만' 적용할 수 있게 해준다는 것입니다.

기존에 우리가 온라인 상에서 공동작업을 수행할 때에는 항상 파일 단위로 작업이 이루어졌습니다. 각자 서로 다른 파일을 가지고 작업을 할 때는 이런 방식이 별 문제가 없었지만, 하나의 파일에서 동시에 작업을 수행하려 할 때는 분명 불편함이 있었습니다. 누군가 파일을 수정했는데 이를 미처 확인하지 못하고 파일을 덮어쓰기 해버렸다던가 하는 일들이 생겼죠.

다른 문제도 있었습니다. 어느 순간부터 코드에 에러가 발생했는데, 그게 무엇을 잘못 수정해서 생긴 에러인지, 그 시점을 정확히 파악하지 못하면 에러를 수정하는 시간이 두배 세배로 늘어나는 일이 비일비재했죠. 그렇다고 계속해서 파일을 백업하자니 귀찮음과 저장공간의 낭비를 감수할 수밖에 없었습니다.

Git은 이러한 문제를 해결하기 위해 만들어졌습니다. Git은 commit 단위로 파일의 변경내역을 저장하며, 파일 갱신시 전체 파일을 덮어쓰기보다 변경사항만 적용할 수 있도록 유도합니다.

이를 위해 commit끼리 변경사항에 충돌하는 부분은 없는지 검사해주기도 하고, 애매한 부분은 사용자가 직접 확인해달라고 요청하기도 합니다. 변경내역이 저장되니까 당연히 일부 변경사항만 되돌리는 것도 가능하죠.

Git은 이러한 문제의식을 갖고 만들어진 다양한 기능들의 집합체입니다. Git의 기능은 정말 많지만, 모든 기능을 한 번에 공부해야 하는 것은 아닙니다.

앞으로의 포스팅은 Git의 기능들에 대한 가이드가 될 텐데요, 여러분이 Git을 사용하면서 그때그때 필요한 부분을 언제든 찾아보고 따라해볼 수 있는 글이 됐으면 좋겠습니다.
