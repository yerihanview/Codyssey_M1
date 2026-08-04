### 도커 볼륨 만들기
```css
yerihan3763@c5r4s7 docker-practice % docker volume create my-volume
my-volume
yerihan3763@c5r4s7 docker-practice % docker volume ls
DRIVER    VOLUME NAME
local     my-volume
```

### 도커 볼륨 마운트한 컨테이너 띄우기
```css
yerihan3763@c5r4s7 docker-practice % docker run -it --name volume-test -v my-volume:/data ubuntu /bin/bash 
```

### 볼륨 마운트 영역에 화일 만들기  
```css
root@f008c161e1c5:/# cd /data 
root@f008c161e1c5:/data# touch volume-test.txt
root@f008c161e1c5:/data# echo "test message" > volume-test.txt 
root@f008c161e1c5:/data# cat volume-test.txt 
test message
root@f008c161e1c5:/data# 
root@f008c161e1c5:/data# exit
exit
```

### 도커 컨테이너 삭제하고, 동일한 볼륨마운트한 다른 컨테이너 띄우기 
```css
yerihan3763@c5r4s7 docker-practice % 
yerihan3763@c5r4s7 docker-practice % docker rm volume-test
volume-test
yerihan3763@c5r4s7 docker-practice % docker ps -a
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
yerihan3763@c5r4s7 docker-practice % 
yerihan3763@c5r4s7 docker-practice % docker run -it --name volume-test2 -v my-volume:/data ubuntu /bin/bash
```

### 새 컨테이너의 볼륨마운트 영역에 앞서 만든 데이타가 남아 있는 지 확인
```css
root@ee02bf8c8d8a:/# 
root@ee02bf8c8d8a:/# cat /data/volume-test.txt 
test message
root@ee02bf8c8d8a:/# exit
exit
```

