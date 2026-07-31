
### Git 버전 확인 : git --version 
```css
yerihan3763@c5r6s7 ~ % git --version
```
### Git 초기화 : git init 
```css
yerihan3763@c5r4s7 ~ % git init
hint: Using 'master' as the name for the initial branch. This default branch name
hint: will change to "main" in Git 3.0. To configure the initial branch name
hint: to use in all of your new repositories, which will suppress this warning,
hint: call:
hint:
hint: 	git config --global init.defaultBranch <name>
hint:
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint:
hint: 	git branch -m <name>
hint:
hint: Disable this message with "git config set advice.defaultBranchName false"
/Users/yerihan3763/.git/ 안의 빈 깃 저장소를 다시 초기화했습니다
```

### Git 사용자 정보 설정 : git config
```css
yerihan3763@c5r4s7 ~ % git config --global user.name "우광택"
yerihan3763@c5r4s7 ~ % git config --global user.email "yerihna@gmail.com"
yerihan3763@c5r4s7 ~ % git config --global --list
user.name=우광택
user.email=yerihna@gmail.com
```

### Git 복제하기 (from github) : git clone
```css
yerihan3763@c5r4s7 ~ % git clone https://github.com/yerihanview/Codyssey_M1
'Codyssey_M1'에 복제합니다...
remote: Enumerating objects: 42, done.
remote: Counting objects: 100% (42/42), done.
remote: Compressing objects: 100% (36/36), done.
remote: Total 42 (delta 11), reused 17 (delta 2), pack-reused 0 (from 0)
오브젝트를 받는 중: 100% (42/42), 27.45 KiB | 6.86 MiB/s, 완료.
델타를 알아내는 중: 100% (11/11), 완료.

yerihan3763@c5r4s7 ~ % ls -la
total 24
drwxr-x---+ 18 yerihan3763  yerihan3763   576  7 31 14:49 .
drwxr-xr-x   8 root         admin         256  7 31 13:54 ..
-r--------   1 yerihan3763  yerihan3763     8  7 31 13:54 .CFUserTextEncoding
drwxr-xr-x   9 yerihan3763  yerihan3763   288  7 31 14:38 .git
-rw-r--r--   1 yerihan3763  yerihan3763    52  7 31 14:42 .gitconfig
-rw-------   1 yerihan3763  yerihan3763    20  7 31 14:46 .lesshst
drwx------+  2 yerihan3763  yerihan3763    64  7 31 13:55 .Trash
drwxr-xr-x   3 yerihan3763  yerihan3763    96  7 31 13:55 .vscode
drwx------   3 yerihan3763  yerihan3763    96  7 31 14:34 .zsh_sessions
drwxr-xr-x   9 yerihan3763  yerihan3763   288  7 31 14:49 Codyssey_M1
drwx------+  3 yerihan3763  yerihan3763    96  7 31 13:54 Desktop
drwx------+  3 yerihan3763  yerihan3763    96  7 31 13:54 Documents
drwx------+  3 yerihan3763  yerihan3763    96  7 31 13:54 Downloads
drwx------@ 76 yerihan3763  yerihan3763  2432  7 31 14:19 Library
drwx------   3 yerihan3763  yerihan3763    96  7 31 13:54 Movies
drwx------+  3 yerihan3763  yerihan3763    96  7 31 13:54 Music
drwx------+  4 yerihan3763  yerihan3763   128  7 31 13:55 Pictures
drwxr-xr-x+  4 yerihan3763  yerihan3763   128  7 31 13:54 Public

yerihan3763@c5r4s7 ~ % ls -al Codyssey_M1 
total 184
drwxr-xr-x   9 yerihan3763  yerihan3763    288  7 31 14:49 .
drwxr-x---+ 18 yerihan3763  yerihan3763    576  7 31 14:49 ..
drwxr-xr-x  12 yerihan3763  yerihan3763    384  7 31 14:49 .git
drwxr-xr-x   4 yerihan3763  yerihan3763    128  7 31 14:49 docker-practice
-rw-r--r--   1 yerihan3763  yerihan3763   1340  7 31 14:49 README.md
-rw-r--r--   1 yerihan3763  yerihan3763   6614  7 31 14:49 step0.log
-rw-r--r--   1 yerihan3763  yerihan3763   9721  7 31 14:49 step1.log
-rw-r--r--   1 yerihan3763  yerihan3763  40502  7 31 14:49 step2.log
-rw-r--r--   1 yerihan3763  yerihan3763  27696  7 31 14:49 step3.log
```

### 현재 폴더에서 VSCode 열기 + VSCode에서 README.md 수정하기
```css
yerihan3763@c5r6s7 Codyssey_M1 % 
yerihan3763@c5r6s7 Codyssey_M1 % code .
```

### 로컬PC에 임시 저장하기 : git add , git commit
```css
yerihan3763@c5r4s7 Codyssey_M1 % touch test.txt
yerihan3763@c5r4s7 Codyssey_M1 % git add test.txt
yerihan3763@c5r4s7 Codyssey_M1 % git commit -m "docs: test.txt 생성"
[main 8996f07] docs: test.txt 생성
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test.txt
```

### github에 저장하기(실패: 권한이 없음)
```css
yerihan3763@c5r6s7 Codyssey_M1 % git push origin main  
Username for 'https://github.com': yerihanview
Password for 'https://yerihanview@github.com': 
remote: Invalid username or token. Password authentication is not supported for Git operations. // 실패
fatal: Authentication failed for 'https://github.com/yerihanview/Codyssey_M1/'
```

### github 연결하기 (github에서 token 발급후, 인증없이 자동 로그인)
```css
yerihan3763@c5r6s7 Codyssey_M1 % git remote set-url origin https://yerihanview:ghp_q72jZyPSCzNj1uAoGk4xu9OVcUl7UPXXXXXX@github.com/yerihanview/Codyssey_M1.git 
yerihan3763@c5r6s7 Codyssey_M1 % 
yerihan3763@c5r6s7 Codyssey_M1 % 
```

### github에 저장하기 (origin: 원격 저장소, main: main branch)
```css
yerihan3763@c5r6s7 Codyssey_M1 % git push origin main
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 6 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 832 bytes | 832.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/yerihanview/Codyssey_M1.git
 * [new branch]      main -> main
```





