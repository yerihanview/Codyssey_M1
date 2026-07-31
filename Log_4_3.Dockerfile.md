### Dockerfile 작성하기 (웹서버)
```css
yerihan3763@c5r4s7 docker-practice % touch Dockerfile
yerihan3763@c5r4s7 docker-practice % vi Dockerfile 
yerihan3763@c5r4s7 docker-practice % cat Dockerfile
FROM nginx:latest
LABEL maintainer="우광택<yerihan@gmail.com>"
COPY index.html /usr/share/nginx/html/index.html
EXPOSE 80
```

### index.html 작성하기
```css
yerihan3763@c5r4s7 docker-practice % touch index.html
yerihan3763@c5r4s7 docker-practice % vi index.html
yerihan3763@c5r4s7 docker-practice % cat index.html
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <title>Docker 실습</title>
  <style>
    body {
      font-family: sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      background-color: #f0f4f8;
    }
    .box {
      text-align: center;
      padding: 40px;
      background: white;
      border-radius: 12px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
    }
    h1 { color: #2d6a4f; }
    p  { color: #555; }
  </style>
</head>
<body>
  <div class="box">
    <h1>Docker 실습 성공!</h1>
    <p>커스텀 nginx 이미지가 정상 동작 중입니다.</p>
    <p>빌드 시각: 2026년</p>
  </div>
</body>
</html>
yerihan3763@c5r4s7 docker-practice % ls -al
total 16
drwxr-xr-x   4 yerihan3763  yerihan3763  128  7 31 16:10 .
drwxr-xr-x  10 yerihan3763  yerihan3763  320  7 31 16:06 ..
-rw-r--r--   1 yerihan3763  yerihan3763  258  7 31 16:09 Dockerfile
-rw-r--r--   1 yerihan3763  yerihan3763  725  7 31 16:10 index.html
```

### 도커 이미지 만들기 : docker build 
```css
yerihan3763@c5r4s7 docker-practice % docker build -t my-nginx:v1 .
zsh: command not found: docker
yerihan3763@c5r4s7 docker-practice % docker build -t my-nginx:v1 .
[+] Building 7.8s (7/7) FINISHED                                           docker:orbstack
 => [internal] load build definition from Dockerfile                                  0.2s
 => => transferring dockerfile: 297B                                                  0.0s
 => [internal] load metadata for docker.io/library/nginx:latest                       2.4s
 => [internal] load .dockerignore                                                     0.2s
 => => transferring context: 2B                                                       0.0s
 => [internal] load build context                                                     0.2s
 => => transferring context: 764B                                                     0.0s
 => [1/2] FROM docker.io/library/nginx:latest@sha256:5a88c9c45479443d7be2eadc894b4ed  4.0s
 => => resolve docker.io/library/nginx:latest@sha256:5a88c9c45479443d7be2eadc894b4ed  0.2s
 => => sha256:5a88c9c45479443d7be2eadc894b4ed0a9801bae03d97a5760ae 10.23kB / 10.23kB  0.0s
 => => sha256:4e5db4761e0ff445f7fd29aad680ad28e8abf7d204895557f145d6 9.09kB / 9.09kB  0.0s
 => => sha256:062e450697faa5f02a3a74eba9864ee4d79bc9cfbd65769fc6cd 29.78MB / 29.78MB  0.6s
 => => sha256:3c7ab7949321f47c96fc0918f9f72e8f51bd452cdef1e0dad959988031 626B / 626B  0.5s
 => => sha256:db4f612f385437d11eb26620a4f1d7efb3ff44e1296a3c21540b30 2.29kB / 2.29kB  0.0s
 => => sha256:82454cdbf456a77f9ff1bb88b121c2a739e38c30ea689c135c7c 33.33MB / 33.33MB  1.1s
 => => sha256:cacfcdd01f309c65d69372716e799ea741065ac1b1e60880b3a6981ae1 955B / 955B  0.7s
 => => extracting sha256:062e450697faa5f02a3a74eba9864ee4d79bc9cfbd65769fc6cdff2c05c  1.1s
 => => sha256:b6698f04e005497a7f495c0719358d43890cb3997ad7b4ab0b06748247 403B / 403B  0.9s
 => => sha256:2bedaf25031a24fb70b9dc2d56cb17139186d1ae5fd2054ecbd0df 1.21kB / 1.21kB  1.0s
 => => sha256:d26f27cc8c41e321394cb3c9a80915d90d5f1f1d3cbbbcda3be00f 1.40kB / 1.40kB  1.2s
 => => extracting sha256:82454cdbf456a77f9ff1bb88b121c2a739e38c30ea689c135c7cca6249e  0.7s
 => => extracting sha256:3c7ab7949321f47c96fc0918f9f72e8f51bd452cdef1e0dad9599880317  0.0s
 => => extracting sha256:cacfcdd01f309c65d69372716e799ea741065ac1b1e60880b3a6981ae10  0.0s
 => => extracting sha256:b6698f04e005497a7f495c0719358d43890cb3997ad7b4ab0b06748247c  0.0s
 => => extracting sha256:2bedaf25031a24fb70b9dc2d56cb17139186d1ae5fd2054ecbd0dfe1a69  0.0s
 => => extracting sha256:d26f27cc8c41e321394cb3c9a80915d90d5f1f1d3cbbbcda3be00f13c53  0.0s
 => [2/2] COPY index.html /usr/share/nginx/html/index.html                            0.4s
 => exporting to image                                                                0.2s
 => => exporting layers                                                               0.1s
 => => writing image sha256:9c3e521516ed55ec34bb48be77cea90d2ddf28ad2bd150d579a99d64  0.0s
 => => naming to docker.io/library/my-nginx:v1                                        0.0s
```

### 생성된 이미지 확인
```css 
yerihan3763@c5r4s7 docker-practice % docker images
REPOSITORY   TAG       IMAGE ID       CREATED         SIZE
my-nginx     v1        9c3e521516ed   7 seconds ago   161MB
```

### 도커 이미지 포트매핑하여 띄우기 
```css
yerihan3763@c5r4s7 docker-practice % docker run -d -p 8080:80 --name my-nginx-container my-nginx:v1
c2a01752e76b9dbfee6047f0e4cfab7100d1cf5a34013a37d068f0de842cec7f
yerihan3763@c5r4s7 docker-practice % 
yerihan3763@c5r4s7 docker-practice % docker ps
CONTAINER ID   IMAGE         COMMAND                   CREATED         STATUS         PORTS                                     NAMES
c2a01752e76b   my-nginx:v1   "/docker-entrypoint.…"   5 seconds ago   Up 4 seconds   0.0.0.0:8080->80/tcp, [::]:8080->80/tcp   my-nginx-container
```


