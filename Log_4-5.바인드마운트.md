### 8080 포트를 사용하는 기존 컨테이너 내리기
```css
yerihan3763@c5r4s7 Pictures % docker stop my-nginx-container
my-nginx-container
yerihan3763@c5r4s7 Pictures % docker rm my-nginx-container
my-nginx-container
```

### index.html이 저장된 폴더로 이동 + 바인드 마운트하여 기동하기 
```css
yerihan3763@c5r4s7 Codyssey_M1 % cd docker-practice 
yerihan3763@c5r4s7 docker-practice % ls -la
total 16
drwxr-xr-x   4 yerihan3763  yerihan3763  128  7 31 16:10 .
drwxr-xr-x  10 yerihan3763  yerihan3763  320  7 31 16:06 ..
-rw-r--r--   1 yerihan3763  yerihan3763  258  7 31 16:09 Dockerfile
-rw-r--r--   1 yerihan3763  yerihan3763  725  7 31 16:10 index.html

yerihan3763@c5r4s7 docker-practice % docker run -d -p 8080:80 -v $(pwd):/usr/share/nginx/html nginx:latest
44287b91fe70b327ec35073448bc27517566b2f566f9700dd0949bcf81d4c13d
```
