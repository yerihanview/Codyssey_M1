### 도커 이미지 포트매핑하여 띄우기 
```css
yerihan3763@c5r4s7 docker-practice % docker run -d -p 8080:80 --name my-nginx-container my-nginx:v1
c2a01752e76b9dbfee6047f0e4cfab7100d1cf5a34013a37d068f0de842cec7f
yerihan3763@c5r4s7 docker-practice % 
yerihan3763@c5r4s7 docker-practice % docker ps
CONTAINER ID   IMAGE         COMMAND                   CREATED         STATUS         PORTS                                     NAMES
c2a01752e76b   my-nginx:v1   "/docker-entrypoint.…"   5 seconds ago   Up 4 seconds   0.0.0.0:8080->80/tcp, [::]:8080->80/tcp   my-nginx-container
```



