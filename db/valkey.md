# Valkey

Redis의 대체 품으로 사용할 인메모리 데이터 저장소.

### Valkey Client 종류
	1. Redis Client
	2. Valkey-Java
	3. Valkey-GLIDE
#### 1. Redis CLient
	Redis 클라이언트는 Redis 서버와 연결하여 데이터를 읽고 쓰는 데 사용되는 라이브러리 또는 도구입니다. 다양한 프로그래밍 언어(예: Python, Java, Node.js 등)에서 사용할 수 있으며, Redis의 명령어를 쉽게 호출하고 결과를 처리할 수 있도록 돕습니다. 이를 통해 개발자는 Redis의 인메모리 데이터베이스 기능을 애플리케이션에 통합할 수 있습니다.
#### 2. Valkey-Java
	Valkey-java는 Valkey의 Java 클라이언트로, Jedis의 포크에서 파생된 것으로, 단순성과 높은 성능을 유지하는 데 중점을 두고 있습니다.
#### 3. Valkey-GLIDE
	Valkey GLIDE는 Valkey를 위한 오픈소스 클라이언트 라이브러리로, Valkey 7.2 이상과 Redis 6.2, 7.0, 7.2를 지원합니다. 안정적이고 신뢰성 있는 연결을 제공하며, 고성능과 고가용성을 목표로 설계되었습니다. AWS의 지원을 받으며, Rust로 작성된 핵심 드라이버 프레임워크를 기반으로 다양한 언어 확장을 지원하여 개발의 일관성을 유지합니다.

### Valeky-Java를 선택한 이유
	  GLIDE보단 Java 앱 용도로 내놓은 Valkey-Java가 본진 아닐까..?
   
### Valkey 사용(Compose)
```yml
#docker-compose.yml
version: '3.8'[[Valkey]]

services:
  valkey:
    container_name: valkey
    image: valkey/valkey:alpine
    ports:
      - "8081:6379"
    volumes:
      - ../valkeydata:/data
    environment:
      VALKEY_EXTRA_FLAGS: '--save 60 1 --loglevel warning'
```
