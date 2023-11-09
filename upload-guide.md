# 주간발표 GitHub 업로드 가이드

**주간발표 깃허브 저장소**
---
[https://github.com/JNU-econovation/weekly_presentation](https://github.com/JNU-econovation/weekly_presentation)


**목차**
---
1. 본인의 레포로 fork 하기
2. git init
3. 개인 저장소와 원격 저장소 연결하기 - remote
4. 원격 저장소의 내용을 가져오기 - pull
5. 브랜치 생성 및 이동
6. 발표 자료 추가하기
7. git add
8. git commit
9. git push
10. pull request



**가이드 진행 순서**
---
**처음** 주간발표 레포에 업로드 하는 경우: 목차의 1번부터 순서대로 진행

**한 번 이상** 올려본 경우: 목차의 4번 진행 후 6~10번 진행


### 1. 본인의 레포로 fork 하기

1-1. fork란?

![Group 1.png](https://github.com/baegyeong/baegyeong/assets/102566546/55e3a495-7524-48b1-960b-5d8563cf8582)

위의 링크에 접속하면, JNU-econovation 계정의 `weekly_presentation` 레포지토리를 볼 수 있습니다.

여기에 바로 자료를 업로드할 수 있는 권한은 없기 때문에, 본인 레포로 **fork**를 해야합니다.

**fork**란, 원본 레포지토리를 본인 계정의 레포지토리로 그대로 복제하는 기능입니다.

1-2. fork하기

![Group 11.png](https://github.com/baegyeong/baegyeong/assets/102566546/161dab94-8ad1-4a81-a58b-3215c852a606)

위의 레포에서 fork를 클릭합니다.

![Group 4.png](https://github.com/JNU-econovation/weekly_presentation/assets/102566546/e591b38c-ee6a-4e14-a0bb-5f29377d44c8)


그럼 이러한 창이 뜨는데, 'copy the main branch only'는 체크 해제 합니다. (학기별로 발료자료 브랜치가 만들어져 있어서, 모두 불러오기 위해서는 체크 해제가 필요합니다.)
밑에 Create fork를 클릭합니다.

![Group 5.png](https://github.com/baegyeong/baegyeong/assets/102566546/9f2bbc59-3efd-474f-9b4c-66f8d364d10d)

본인의 계정에서 복제본이 생성된 것을 확인할 수 있습니다.


### 2. git init

2-1. 본인의 PC에 폴더를 하나 생성합니다.

2-2. 윈도우 유저라면 git bash, 맥 유저라면 터미널을 실행합니다.

2-3. 1번에서 생성한 폴더로 이동합니다. (`cd` 명령어 사용)

2-4. git init 명령어를 입력하여 초기화합니다.

![Untitled](https://github.com/baegyeong/baegyeong/assets/102566546/fab779db-0396-49a6-9325-979c87a992ce)

저는 바탕화면(desktop)에 econo-presentation 폴더를 생성한 후 git init 명령어를 실행했습니다.


### 3. 개인 저장소와 원격 저장소 연결하기 - remote

3-1. 원격 저장소(fork 해 온 저장소) 주소를 복사합니다.

에코노 계정의 레포가 아닌 본인의 계정에 있는, 즉 fork 해 온 레포의 주소를 복사해야 합니다.

![Group 12.png](https://github.com/baegyeong/baegyeong/assets/102566546/aaec260a-f3bd-4e0d-b09c-acefafe101fc)

3-2. 저장소 추가

```bash
$ git remote add origin "repo 주소"
```

![Untitled](https://github.com/baegyeong/baegyeong/assets/102566546/b2e457f9-3863-47da-9a47-a04780b06033)

‘복사한 저장소의 주소를, `origin` 이라는 이름으로 개인 저장소에 추가하겠다!’라는 의미입니다.

3-3. 추가된 저장소 확인

```bash
git remote -v
```

![Untitled](https://github.com/baegyeong/baegyeong/assets/102566546/5294f27a-1801-48c9-a9e7-966584ac9e1d)

`origin` 이라는 이름으로 저장소의 주소가 잘 연결 된 것을 확인할 수 있습니다.


### 4. 원격 저장소의 내용을 가져오기 - pull

위의 단계까지는 단순한 연결을 한 것이므로, 원격 저장소의 폴더 혹은 파일을 내 컴퓨터로 가져오기 위해 pull 명령어를 사용합니다.

```bash
git pull origin [현재 학기 브랜치]
```

![Untitled](https://github.com/JNU-econovation/weekly_presentation/assets/102566546/48ccee65-a756-49d5-8c0d-376eaf3e5fd8)

‘origin(위에서 연결한 주소)의 `[현재 학기 브랜치]`에 속한 내용을 가져오겠다!’는 의미입니다.
그림에서 2023-2처럼 현재 학기의 브랜치를 작성해주세요.


### 5. 브랜치 생성 및 이동

5-1. 브랜치 생성

main에서 작업하기보다는, 본인의 팀명으로 된 브랜치를 생성하여 작업합니다.

```bash
git branch 팀명 # 팀명 생성
git branch # 브랜치 목록 확인
```

![Untitled](https://github.com/baegyeong/baegyeong/assets/102566546/db54a430-42ae-411e-a7cf-6ff29f79f456)

git branch 명령어를 통해 브랜치가 잘 생성이 된 것을 확인할 수 있습니다.

하지만 지금 브랜치의 위치가 master 이므로 팀명 브랜치로 이동해볼까요?

5-2. 브랜치 이동

git switch 명령어를 통해 브랜치가 잘 이동한 것을 확인할 수 있습니다.

```bash
git switch 팀명
```

![Untitled](https://github.com/baegyeong/baegyeong/assets/102566546/8fcb76f5-e52f-4153-a21c-80a5374b7b60)


### 6. 발표 자료 추가하기

![Untitled](https://github.com/baegyeong/baegyeong/assets/102566546/c7c96486-7d25-45df-a762-a4f9bd308ce7)

발표 날짜, 발표 팀을 잘 확인해서 해당 폴더에 발표자료를 추가합니다.

예를 들어 오늘이 5월 19일 B팀의 발표라면, `2023-1/B_team/2nd/팀명` 폴더에 발표자료를 추가합니다.

일단, 팀명 폴더부터 만들어볼까요?

실제 파일탐색기에서 편하게 폴더를 생성해도 되지만, CLI 환경에 익숙해지기 위해서는 명령어로 폴더를 만들어보세요~!

⚠️ **폴더를 만들기 위해서는 3가지의 명령어만 기억해주시면 됩니다.** ⚠️

1. ls: 현재 위치의 폴더 내용 리스트 출력
2. cd: 현재 작업 중인 폴더의 위치 이동
3. mkdir: 폴더 생성

![Group 13.png](https://github.com/baegyeong/baegyeong/assets/102566546/151525bf-3e1f-4eba-bfca-7a61fe7333c5)

![Untitled](https://github.com/baegyeong/baegyeong/assets/102566546/20dbc8ed-b8cf-4ada-b558-0fc96782d60d)

실제 파일탐색기에서 준비한 발표자료를 추가합니다.


### 7. git add

레포에 추가할 파일을 입력합니다.

```bash
git add "추가한 파일 이름"
```

![Untitled](https://github.com/baegyeong/baegyeong/assets/102566546/192806ca-7380-47a9-808a-ba4f8dbd7295)

`git status`명령어를 통해 파일이 잘 추가됐는지 확인합니다. (위의 화면과 같이 new file이 등록되면 성공)

```bash
git status
```

![Untitled](https://github.com/baegyeong/baegyeong/assets/102566546/7efa7da1-787c-48f9-9c7a-6bf2c4058239)


### 8. git commit

커밋은 변경사항을 기록하는 것입니다! 주간발표 레포에서는 `docs: 팀명`으로 메시지를 통일합니다.

```bash
git commit -m "docs: 팀명"
```

![Untitled](https://github.com/baegyeong/baegyeong/assets/102566546/d10fdd50-6434-4401-9fe4-64a78d3f2083)


### 9. git push

origin(원격 저장소)에 변경사항을 push 합니다.

```bash
git push origin 팀명 # 여기서 팀명은 4번에서 생성한 브랜치 이름
```

![Untitled](https://github.com/baegyeong/baegyeong/assets/102566546/f01a54b3-0d70-463a-ab80-f41d3c05a78e)


### 10. pull request

이제, 본인 계정의 레포에서 변경한 사항을 에코노 계정의 레포로 공유하면 됩니다.

![Group 9.png](https://github.com/baegyeong/baegyeong/assets/102566546/2d1ddc89-8829-48b7-9d97-f33fba64934e)

다시 본인 계정의 레포로 돌아와서 확인하면, 다음과 같은 화면이 보이는 것을 확인할 수 있습니다!

Compare&pull request 버튼을 클릭합니다.

![Group 10.png](https://github.com/JNU-econovation/weekly_presentation/assets/102566546/656a2935-11f9-4457-a327-576d3d919dfe)

밑의 create pull request 버튼을 클릭하면 주간발표 업로드가 마무리 됩니다!
