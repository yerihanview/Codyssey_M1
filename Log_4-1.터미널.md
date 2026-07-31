### 개발 환경 정보 확인
```css
yerihan3763@c5r6s7 Codyssey_M1 % sw_vers
ProductName:		macOS
ProductVersion:		15.7.7
BuildVersion:		24G720

yerihan3763@c5r6s7 Codyssey_M1 % echo $SHELL
/bin/zsh
```

### echo, cat, cp, ls -al, mv
```css
yerihan3763@c4r2s8 Codyssey_M1 % echo "Hello, Codyssey!" > practice/hello.txt 
dquote> 
yerihan3763@c4r2s8 Codyssey_M1 % 

yerihan3763@c4r2s8 Codyssey_M1 % echo 'Hello, Codyssey!' > practice/hello.txt 

yerihan3763@c4r2s8 Codyssey_M1 % cat practice/hello.txt 
Hello, Codyssey!

yerihan3763@c4r2s8 Codyssey_M1 % cp practice/hello.txt practice/hello_copy.txt
yerihan3763@c4r2s8 Codyssey_M1 % ls -al practice 
titotal 16
drwxr-xr-x  6 yerihan3763  yerihan3763  192  7 30 09:29 .
drwxr-xr-x  6 yerihan3763  yerihan3763  192  7 30 09:14 ..
-rw-r--r--  1 yerihan3763  yerihan3763   17  7 30 09:29 hello_copy.txt
-rw-r--r--  1 yerihan3763  yerihan3763   17  7 30 09:28 hello.txt
drwxr-xr-x  2 yerihan3763  yerihan3763   64  7 30 09:14 sub
-rw-r--r--  1 yerihan3763  yerihan3763    0  7 30 09:15 world.txt

yerihan3763@c4r2s8 Codyssey_M1 % mv practice/hello.txt practice/renamed.txt
yerihan3763@c4r2s8 Codyssey_M1 % 
yerihan3763@c4r2s8 Codyssey_M1 % ls -al
total 24
drwxr-xr-x   6 yerihan3763  yerihan3763   192  7 30 09:14 .
drwxr-x---+ 15 yerihan3763  yerihan3763   480  7 30 09:11 ..
drwxr-xr-x  12 yerihan3763  yerihan3763   384  7 30 09:11 .git
drwxr-xr-x   6 yerihan3763  yerihan3763   192  7 30 09:30 practice
-rw-r--r--   1 yerihan3763  yerihan3763   956  7 30 09:11 README.md
-rw-r--r--   1 yerihan3763  yerihan3763  6614  7 30 09:11 step1.log
yerihan3763@c4r2s8 Codyssey_M1 % ls -al practice 
total 16
drwxr-xr-x  6 yerihan3763  yerihan3763  192  7 30 09:30 .
drwxr-xr-x  6 yerihan3763  yerihan3763  192  7 30 09:14 ..
-rw-r--r--  1 yerihan3763  yerihan3763   17  7 30 09:29 hello_copy.txt
-rw-r--r--  1 yerihan3763  yerihan3763   17  7 30 09:28 renamed.txt
drwxr-xr-x  2 yerihan3763  yerihan3763   64  7 30 09:14 sub
-rw-r--r--  1 yerihan3763  yerihan3763    0  7 30 09:15 world.txt
```

### rm
```css
yerihan3763@c4r2s8 Codyssey_M1 % rm practice/renamed.txt 
yerihan3763@c4r2s8 Codyssey_M1 % ls -la
total 24
drwxr-xr-x   6 yerihan3763  yerihan3763   192  7 30 09:14 .
drwxr-x---+ 15 yerihan3763  yerihan3763   480  7 30 09:11 ..
drwxr-xr-x  12 yerihan3763  yerihan3763   384  7 30 09:11 .git
drwxr-xr-x   5 yerihan3763  yerihan3763   160  7 30 09:31 practice
-rw-r--r--   1 yerihan3763  yerihan3763   956  7 30 09:11 README.md
-rw-r--r--   1 yerihan3763  yerihan3763  6614  7 30 09:11 step1.log
yerihan3763@c4r2s8 Codyssey_M1 % rm -r practice/subdir
rm: practice/subdir: No such file or directory
yerihan3763@c4r2s8 Codyssey_M1 % rm -r practice/sub 
yerihan3763@c4r2s8 Codyssey_M1 % ls -al practice 
total 8
drwxr-xr-x  4 yerihan3763  yerihan3763  128  7 30 09:31 .
drwxr-xr-x  6 yerihan3763  yerihan3763  192  7 30 09:14 ..
-rw-r--r--  1 yerihan3763  yerihan3763   17  7 30 09:29 hello_copy.txt
-rw-r--r--  1 yerihan3763  yerihan3763    0  7 30 09:15 world.txt
```

### 디렉토리 이동
```css
yerihan3763@c4r2s8 Codyssey_M1 % cd ~                              
yerihan3763@c4r2s8 ~ % pwd
yerihan3763@c4r2s8 ~ % cd Codyssey_M1 
yerihan3763@c4r2s8 Codyssey_M1 % cd ..
yerihan3763@c4r2s8 ~ % cd ..
yerihan3763@c4r2s8 /Users % pwd
/Users
yerihan3763@c4r2s8 /Users % ls -la
total 0
drwxr-xr-x   9 root            admin           288  7 30 09:02 .
drwxr-xr-x  22 root            wheel           704  2  1 15:03 ..
-rw-r--r--   1 root            wheel             0  2  1 15:03 .localized
drwxr-x---+ 21 cody            staff           672  7 30 07:21 cody
drwxr-x---+ 13 keodnd07043654  keodnd07043654  416  7 27 16:49 keodnd07043654
drwxr-x---+ 21 pdg10135527     pdg10135527     672  7 29 17:12 pdg10135527
drwxr-x---+ 13 potago1238614   potago1238614   416  7 28 16:42 potago1238614
drwxrwxrwt   4 root            wheel           128  4 29 15:43 Shared
drwxr-x---+ 15 yerihan3763     yerihan3763     480  7 30 09:11 yerihan3763
```

### 권한 설정
```css
yerihan3763@c4r2s8 practice % chmod 755 hello_copy.txt 
yerihan3763@c4r2s8 practice % ls -al hello_copy.txt 
-rwxr-xr-x  1 yerihan3763  yerihan3763  17  7 30 09:29 hello_copy.txt

yerihan3763@c4r2s8 practice % chmod 644 hello_copy.txt 
yerihan3763@c4r2s8 practice % ls -al hello_copy.txt 
-rw-r--r--  1 yerihan3763  yerihan3763  17  7 30 09:29 hello_copy.txt

yerihan3763@c4r2s8 practice % chmod 600 world.txt 
yerihan3763@c4r2s8 practice % ls -al world.txt 
-rw-------  1 yerihan3763  yerihan3763  0  7 30 09:15 world.txt

