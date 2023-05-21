# git log 공부하기

---

- [git log 공부하기](#git-log-공부하기)
  - [Log · History](#log--history)
  - [지나온 기록들을 확인하기](#지나온-기록들을-확인하기)
    - [git log](#git-log)
    - [git log —patch, git log -p](#git-log-patch-git-log--p)
    - [git log —oneline](#git-log-oneline)
    - [git log —oneline —reverse](#git-log-oneline-reverse)
  - [Formatting](#formatting)
    - [git log —pretty](#git-log-pretty)
    - [git log —pretty=oneline](#git-log-prettyoneline)
    - [git log —pretty=format:"%h - %an %ar %s"](#git-log-prettyformath---an-ar-s)
    - [git log --pretty=format:"%h %s" --graph](#git-log---prettyformath-s---graph)
    - [git log --graph --all --pretty=format:'%C(yellow)\[%ad\]%C(reset) %C(green)\[%h\]%C(reset) | %C(white)%s %C(bold red){{%an}}%C(reset) %C(blue)%d%C(reset)' --date=short](#git-log---graph---all---prettyformatcyellowadcreset-cgreenhcreset--cwhites-cbold-redancreset-cbluedcreset---dateshort)
  - [Filtering](#filtering)
    - [git log -2](#git-log--2)
    - [git log —author=’dataliteracy’](#git-log-authordataliteracy)
    - [git log —before=”2023-05-21”](#git-log-before2023-05-21)
    - [git log —after=”one week ago”](#git-log-afterone-week-ago)
    - [git log —grep=”message”](#git-log-grepmessage)
    - [git log -S=”code”](#git-log--scode)
    - [git log about.txt](#git-log-abouttxt)
  - [History of a file](#history-of-a-file)
    - [git log about.txt](#git-log-abouttxt-1)
    - [git log —patch about.txt](#git-log-patch-abouttxt)
  - [HEAD · Hash code](#head--hash-code)
    - [git log HEAD](#git-log-head)
    - [git log HEAD~1](#git-log-head1)
    - [git log hash](#git-log-hash)
  - [Viewing a commit](#viewing-a-commit)
    - [git show HEAD](#git-show-head)
    - [git show hash](#git-show-hash)
    - [git show hash file.txt](#git-show-hash-filetxt)
  - [Comparing](#comparing)
    - [git diff hash1 hash2](#git-diff-hash1-hash2)
    - [git diff hash1 hash2 about.txt](#git-diff-hash1-hash2-abouttxt)

---

## Log · History

## 지나온 기록들을 확인하기

### git log

모든 커밋들의 이력을 확인한다.

```bash
git log
```

```bash
commit 8f626589908ea64f13764727701c03c5f520b40f (HEAD -> log, origin/log)
Author: DataCodeLiteracy <dataliteracy@icloud.com>
Date:   Sun May 21 14:29:44 2023 +0900

    rename: 폴더 이동

commit e086b0fbb18e18e4941e96c06b1aed1686cbdbb8
Author: DataCodeLiteracy <dataliteracy@icloud.com>
Date:   Sun May 21 14:18:48 2023 +0900

    log 예제 파일 등록록_ft.드림코딩

commit 8d37ca7dfee8562c12201a20786af6813cb4a07d (origin/main, origin/HEAD, main)
Author: LeeJongHyun <dataliteracy@icloud.com>
Date:   Sun May 21 14:17:05 2023 +0900
		Initial commit
```

### git log —patch, git log -p

각 커밋들의 차이점을 비교하여 보여준다.

```bash
git log —patch
git log -p
```

```bash
commit 8f626589908ea64f13764727701c03c5f520b40f (HEAD -> log, origin/log)
Author: DataCodeLiteracy <dataliteracy@icloud.com>
Date:   Sun May 21 14:29:44 2023 +0900

    rename: 폴더 이동

diff --git a/git-log/about.txt "b/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/about.txt"
similarity index 100%
rename from git-log/about.txt
rename to "git-log/\353\223\234\353\246\274\354\275\224\353\224\251/about.txt"
diff --git a/git-log/light_theme.txt "b/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/light_theme.txt"
similarity index 100%
rename from git-log/light_theme.txt
rename to "git-log/\353\223\234\353\246\274\354\275\224\353\224\251/light_theme.txt"
diff --git a/git-log/login_module.txt "b/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/login_module.txt"
similarity index 100%
rename from git-log/login_module.txt
rename to "git-log/\353\223\234\353\246\274\354\275\224\353\224\251/login_module.txt"
diff --git a/git-log/project_init.config "b/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/project_init.config"
similarity index 100%
rename from git-log/project_init.config
rename to "git-log/\353\223\234\353\246\274\354\275\224\353\224\251/project_init.config"
diff --git a/git-log/user_repository.txt "b/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/user_repository.txt"
similarity index 100%
rename from git-log/user_repository.txt
rename to "git-log/\353\223\234\353\246\274\354\275\224\353\224\251/user_repository.txt"
diff --git a/git-log/welcome.txt "b/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/welcome.txt"
similarity index 100%
rename from git-log/welcome.txt
rename to "git-log/\353\223\234\353\246\274\354\275\224\353\224\251/welcome.txt"

commit e086b0fbb18e18e4941e96c06b1aed1686cbdbb8
Author: DataCodeLiteracy <dataliteracy@icloud.com>
Date:   Sun May 21 14:18:48 2023 +0900

    log 예제 파일 등록록_ft.드림코딩

diff --git a/git-log/about.txt b/git-log/about.txt
new file mode 100644
index 0000000..31c556b
--- /dev/null
+++ b/git-log/about.txt
```

### git log —oneline

커밋들의 이력을 한 줄로 축약해서 보여준다.

```bash
git log —oneline
```

```bash
8f62658 (HEAD -> log, origin/log) rename: 폴더 이동
e086b0f log 예제 파일 등록록_ft.드림코딩
8d37ca7 (origin/main, origin/HEAD, main) Initial commit
```

### git log —oneline —reverse

oneline을 반대로 뒤집어서 보여준다.

```bash
git log —oneline —reverse
```

```bash
8d37ca7 (origin/main, origin/HEAD, main) Initial commit
e086b0f log 예제 파일 등록록_ft.드림코딩
8f62658 (HEAD -> log, origin/log) rename: 폴더 이동
```

```bash
git log
git log --patch
git log -p
git log --oneline
git log --oneline --reverse
```

## Formatting

### git log —pretty

**`git log`** 출력 형식을 사용자 지정 형식으로 변경하는 옵션

```bash
commit 8f626589908ea64f13764727701c03c5f520b40f (HEAD -> log, origin/log)
Author: DataCodeLiteracy <dataliteracy@icloud.com>
Date:   Sun May 21 14:29:44 2023 +0900

    rename: 폴더 이동

commit e086b0fbb18e18e4941e96c06b1aed1686cbdbb8
Author: DataCodeLiteracy <dataliteracy@icloud.com>
Date:   Sun May 21 14:18:48 2023 +0900

    log 예제 파일 등록록_ft.드림코딩

commit 8d37ca7dfee8562c12201a20786af6813cb4a07d (origin/main, origin/HEAD, main)
Author: LeeJongHyun <dataliteracy@icloud.com>
Date:   Sun May 21 14:17:05 2023 +0900

    Initial commit
```

### git log —pretty=oneline

oneline으로 지정, 즉 git log —oneline과 같다.

```bash
8f626589908ea64f13764727701c03c5f520b40f (HEAD -> log, origin/log) rename: 폴더 이동
e086b0fbb18e18e4941e96c06b1aed1686cbdbb8 log 예제 파일 등록록_ft.드림코딩
8d37ca7dfee8562c12201a20786af6813cb4a07d (origin/main, origin/HEAD, main) Initial commit
```

### git log —pretty=format:"%h - %an %ar %s"

원하는 형식으로 포맷팅

```bash
%h: 커밋 해시(단축 버전)
-: 구분 기호(하이픈)
%an: 작성자 이름
%ar: 상대적인 작성 날짜
%s: 커밋 메시지 요약
```

```bash
8f62658 - DataCodeLiteracy 42분 전 rename: 폴더 이동
e086b0f - DataCodeLiteracy 53분 전 log 예제 파일 등록록_ft.드림코딩
8d37ca7 - LeeJongHyun 55분 전 Initial commit
```

### git log --pretty=format:"%h %s" --graph

git history랑 같은데 포맷팅을 할 수 있는 것 같음..

다른 예시로는 이렇게 표현됨.. 아직은 브랜치가 여러개가 아니라.. 한 줄기로 나옴..

```bash
* 4578a3d Add feature A
| * 682f2e1 Update README
| * d35a907 Add new file
|/
* f3a7b10 Initial commit
```

```bash
* 8f62658 rename: 폴더 이동
* e086b0f log 예제 파일 등록록_ft.드림코딩
* 8d37ca7 Initial commit
```

### git log --graph --all --pretty=format:'%C(yellow)[%ad]%C(reset) %C(green)[%h]%C(reset) | %C(white)%s %C(bold red){{%an}}%C(reset) %C(blue)%d%C(reset)' --date=short

가독성이 좋게 colorful하고 잘 정리정돈 되어 있는 느낌으로 원하는 대로 포맷팅!

![](https://velog.velcdn.com/images/dataliteracy/post/9e0e5430-67f6-4ab9-ac5f-43fcf93dba9f/image.png)

```bash
%C(yellow)[%ad]%C(reset): 커밋 날짜를 노란색으로 출력하고, [날짜] 형식으로 표시합니다. %ad는 커밋의 날짜를 나타내며, yellow는 출력에 사용할 색상입니다.
%C(green)[%h]%C(reset): 커밋 해시를 초록색으로 출력하고, [해시] 형식으로 표시합니다. %h는 커밋의 단축 해시를 나타내며, green은 출력에 사용할 색상입니다.
|: 구분자로 파이프 기호(|)를 사용하여 각 커밋 정보를 구분합니다.
%C(white)%s: 커밋 메시지 요약을 흰색으로 출력합니다. %s는 커밋 메시지의 요약을 나타내며, white는 출력에 사용할 색상입니다.
%C(bold red){{%an}}%C(reset): 커밋 작성자의 이름을 굵은 빨간색으로 출력합니다. %an은 커밋 작성자의 이름을 나타내며, bold red는 출력에 사용할 색상입니다.
%C(blue)%d%C(reset): 브랜치와 태그 정보를 파란색으로 출력합니다. %d는 브랜치와 태그 정보를 나타내며, blue는 출력에 사용할 색상입니다.
--date=short: 커밋 날짜를 축약된 형식으로 출력합니다. 예를 들어, 2023-05-10 대신 2023-05-10 형식으로 출력됩니다.
```

```bash
git log --pretty=oneline
git log --pretty=format:"%h - %an %ar %s"
git log --pretty=format:"%h %s" --graph
git log --graph --all --pretty=format:'%C(yellow)[%ad]%C(reset) %C(green)[%h]%C(reset) | %C(white)%s %C(bold red){{%an}}%C(reset) %C(blue)%d%C(reset)' --date=short
```

## Filtering

### git log -2

마지막 기록 2개를 보여준다.

```bash
commit 8f626589908ea64f13764727701c03c5f520b40f (HEAD -> log, origin/log)
Author: DataCodeLiteracy <dataliteracy@icloud.com>
Date:   Sun May 21 14:29:44 2023 +0900

    rename: 폴더 이동

commit e086b0fbb18e18e4941e96c06b1aed1686cbdbb8
Author: DataCodeLiteracy <dataliteracy@icloud.com>
Date:   Sun May 21 14:18:48 2023 +0900

    log 예제 파일 등록록_ft.드림코딩
```

### git log —author=’dataliteracy’

명시한 작성자가 반영한 커밋들만 보여준다.

```bash
dataliteracy@MacBook-Air  ~/프로그래밍 공부/드림코딩/Git 마스터 과정/LearningGit   log  git log --state
commit 8f626589908ea64f13764727701c03c5f520b40f (HEAD -> log, origin/log)
Author: DataCodeLiteracy <dataliteracy@icloud.com>
Date:   Sun May 21 14:29:44 2023 +0900

    rename: 폴더 이동

commit e086b0fbb18e18e4941e96c06b1aed1686cbdbb8
Author: DataCodeLiteracy <dataliteracy@icloud.com>
Date:   Sun May 21 14:18:48 2023 +0900

    log 예제 파일 등록록_ft.드림코딩

commit 8d37ca7dfee8562c12201a20786af6813cb4a07d (origin/main, origin/HEAD, main)
Author: LeeJongHyun <dataliteracy@icloud.com>
Date:   Sun May 21 14:17:05 2023 +0900

    Initial commit
```

### git log —before=”2023-05-21”

특정 날짜 포함해서 그 이전에 발생한 커밋들의 이력을 보여준다.

### git log —after=”one week ago”

일주일 전부터 현재까지 커밋들을 조회한다.

### git log —grep=”message”

특정 메세지를 가지고 있는 커밋들을 조회한다.

### git log -S=”code”

**`git log -S="code"`** 명령어는 변경 내용에서 특정 문자열인 "code"가 포함된 커밋을 조회하는 명령어입니다.

**`S="code"`** 옵션은 변경 내용에서 "code"라는 문자열이 추가되거나 제거된 커밋을 찾아서 출력합니다. 이 옵션을 사용하면 해당 문자열이 포함된 커밋들만을 조회할 수 있습니다.

→ 하지만 아직 정확하게 어떻게 동작하는지 확인하지 못했다.

### git log about.txt

특정 파일의 로그만 보여준다.

```bash
commit e065954435e3f796c8a399466e941fc50b74f43c (HEAD -> log, origin/log)
Author: DataCodeLiteracy <dataliteracy@icloud.com>
Date:   Sun May 21 15:36:42 2023 +0900

    git log -S 명령어 확인하기

commit 8f626589908ea64f13764727701c03c5f520b40f
Author: DataCodeLiteracy <dataliteracy@icloud.com>
Date:   Sun May 21 14:29:44 2023 +0900

    rename: 폴더 이동
```

```bash
git log -2
git log --author="ellie"
git log --before="2020-09-29"
git log --after="one week ago"
git log --grep="message"
git log -S="code"
git log file.txt
```

## History of a file

### git log about.txt

### git log —patch about.txt

차이점을 비교하면서 특정 파일의 커밋을 전부 보여준다.

```bash
commit e065954435e3f796c8a399466e941fc50b74f43c (HEAD -> log, origin/log)
Author: DataCodeLiteracy <dataliteracy@icloud.com>
Date:   Sun May 21 15:36:42 2023 +0900

    git log -S 명령어 확인하기

diff --git "a/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/about.txt" "b/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/about.txt"
index 31c556b..7f4f291 100644
--- "a/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/about.txt"
+++ "b/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/about.txt"
@@ -1 +1,3 @@
 about page
+
+add code
\ No newline at end of file

commit 8f626589908ea64f13764727701c03c5f520b40f
Author: DataCodeLiteracy <dataliteracy@icloud.com>
Date:   Sun May 21 14:29:44 2023 +0900

    rename: 폴더 이동

diff --git "a/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/about.txt" "b/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/about.txt"
new file mode 100644
index 0000000..31c556b
--- /dev/null
+++ "b/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/about.txt"
@@ -0,0 +1 @@
+about page
```

```bash
git log file.txt
git log --patch file.txt
```

## HEAD · Hash code

### git log HEAD

HEAD가 가리키고 있는 커밋부터 지난 커밋까지 전부 보여준다.

```bash
commit e065954435e3f796c8a399466e941fc50b74f43c (HEAD -> log, origin/log)
Author: DataCodeLiteracy <dataliteracy@icloud.com>
Date:   Sun May 21 15:36:42 2023 +0900

    git log -S 명령어 확인하기

commit 8f626589908ea64f13764727701c03c5f520b40f
Author: DataCodeLiteracy <dataliteracy@icloud.com>
Date:   Sun May 21 14:29:44 2023 +0900

    rename: 폴더 이동

commit e086b0fbb18e18e4941e96c06b1aed1686cbdbb8
Author: DataCodeLiteracy <dataliteracy@icloud.com>
Date:   Sun May 21 14:18:48 2023 +0900

    log 예제 파일 등록록_ft.드림코딩

commit 8d37ca7dfee8562c12201a20786af6813cb4a07d (origin/main, origin/HEAD, main)
Author: LeeJongHyun <dataliteracy@icloud.com>
Date:   Sun May 21 14:17:05 2023 +0900

    Initial commit
```

### git log HEAD~1

HEAD로부터 1 떨어진 커밋부터 지나온 커밋까지 전부 보여준다.

```bash
commit 8f626589908ea64f13764727701c03c5f520b40f
Author: DataCodeLiteracy <dataliteracy@icloud.com>
Date:   Sun May 21 14:29:44 2023 +0900

    rename: 폴더 이동

commit e086b0fbb18e18e4941e96c06b1aed1686cbdbb8
Author: DataCodeLiteracy <dataliteracy@icloud.com>
Date:   Sun May 21 14:18:48 2023 +0900

    log 예제 파일 등록록_ft.드림코딩

commit 8d37ca7dfee8562c12201a20786af6813cb4a07d (origin/main, origin/HEAD, main)
Author: LeeJongHyun <dataliteracy@icloud.com>
Date:   Sun May 21 14:17:05 2023 +0900

    Initial commit
```

### git log hash

특정 해쉬값을 가지고 있는 커밋 이후부터 전부 보여준다.

```bash
commit 387ae6e9306815d7ea53773916c5bdf313025469 (origin/conflict, conflict)
Author: DataCodeLiteracy <dataliteracy@icloud.com>
Date:   Sun May 21 14:39:24 2023 +0900

    conflict 예제 파일 등록_ft.드림코딩

commit 8d37ca7dfee8562c12201a20786af6813cb4a07d (origin/main, origin/HEAD, main)
Author: LeeJongHyun <dataliteracy@icloud.com>
Date:   Sun May 21 14:17:05 2023 +0900

    Initial commit
```

```bash
git log HEAD
git log HEAD~1
git log hash
```

## Viewing a commit

### git show HEAD

HEAD에 대해 자세하게 보여주는 것 같다.

```bash
commit e065954435e3f796c8a399466e941fc50b74f43c (HEAD -> log, origin/log)
Author: DataCodeLiteracy <dataliteracy@icloud.com>
Date:   Sun May 21 15:36:42 2023 +0900

    git log -S 명령어 확인하기

diff --git "a/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/about.txt" "b/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/about.txt"
index 31c556b..7f4f291 100644
--- "a/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/about.txt"
+++ "b/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/about.txt"
@@ -1 +1,3 @@
 about page
+
+add code
\ No newline at end of file
```

### git show hash

특정 hash값을 가지고 있는 커밋에 대해 자세하게 보여준다.

```bash
commit 8f626589908ea64f13764727701c03c5f520b40f
Author: DataCodeLiteracy <dataliteracy@icloud.com>
Date:   Sun May 21 14:29:44 2023 +0900

    rename: 폴더 이동

diff --git a/git-log/about.txt "b/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/about.txt"
similarity index 100%
rename from git-log/about.txt
rename to "git-log/\353\223\234\353\246\274\354\275\224\353\224\251/about.txt"
diff --git a/git-log/light_theme.txt "b/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/light_theme.txt"
similarity index 100%
rename from git-log/light_theme.txt
rename to "git-log/\353\223\234\353\246\274\354\275\224\353\224\251/light_theme.txt"
diff --git a/git-log/login_module.txt "b/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/login_module.txt"
similarity index 100%
rename from git-log/login_module.txt
rename to "git-log/\353\223\234\353\246\274\354\275\224\353\224\251/login_module.txt"
diff --git a/git-log/project_init.config "b/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/project_init.config"
similarity index 100%
rename from git-log/project_init.config
rename to "git-log/\353\223\234\353\246\274\354\275\224\353\224\251/project_init.config"
diff --git a/git-log/user_repository.txt "b/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/user_repository.txt"
similarity index 100%
rename from git-log/user_repository.txt
rename to "git-log/\353\223\234\353\246\274\354\275\224\353\224\251/user_repository.txt"
diff --git a/git-log/welcome.txt "b/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/welcome.txt"
similarity index 100%
rename from git-log/welcome.txt
rename to "git-log/\353\223\234\353\246\274\354\275\224\353\224\251/welcome.txt"
```

### git show hash file.txt

변경사항이 발생한 파일에 대해서 특정 HASH값에 대해서 커밋 이력을 보여주는 것 같다.

```bash
commit e065954435e3f796c8a399466e941fc50b74f43c (HEAD -> log, origin/log)
Author: DataCodeLiteracy <dataliteracy@icloud.com>
Date:   Sun May 21 15:36:42 2023 +0900

    git log -S 명령어 확인하기

diff --git "a/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/about.txt" "b/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/about.txt"
index 31c556b..7f4f291 100644
--- "a/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/about.txt"
+++ "b/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/about.txt"
@@ -1 +1,3 @@
 about page
+
+add code
\ No newline at end of file
```

```bash
git show HEAD
git show hash
git show hash file.txt
```

## Comparing

### git diff hash1 hash2

hash1과 hash2를 비교한다.

```bash
diff --git "a/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/about.txt" "b/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/about.txt"
index 7f4f291..31c556b 100644
--- "a/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/about.txt"
+++ "b/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/about.txt"
@@ -1,3 +1 @@
 about page
-
-add code
\ No newline at end of file
```

### git diff hash1 hash2 about.txt

특정 파일에서 hash간에 다른 점을 비교한다.

```bash
diff --git "a/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/about.txt" "b/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/about.txt"
index 7f4f291..31c556b 100644
--- "a/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/about.txt"
+++ "b/git-log/\353\223\234\353\246\274\354\275\224\353\224\251/about.txt"
@@ -1,3 +1 @@
 about page
-
-add code
\ No newline at end of file
```

```bash
git diff hash1 hash2
git diff hash1 hash2 file.txt
```
