#### compose 세팅
1. 빌드 결과물 `jar war react/dist 등등..` 을 끄집어와서 폴더에 놔둔다.
2. `docker image`를 만들 수 있게  compose파일을 작성한다
```
#docker-compose.yml
version: '3.8'
services:
  nginx:
    image: nginx:alpine #경량화 버전
    ports:
      - "8080:80"
    volumes:
      - ../buildFile/dist:/usr/share/nginx/html #React 빌드 폴더 위치
      - ../buildFile/nginx.conf:/etc/nginx/conf.d/default.conf #nginx 설정 위치
```
3.  작성이 완료된 디렉토리에서 `sudo dokcer compose up`
