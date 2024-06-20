# 실행 방법
### 1. 일반 환경에서 실행 방법
```shell
uvicorn main:app
```

### 2. Docker 컨테이너로 실행 방법

```shell
# Dockerfile 을 기반으로 Docker 이미지를 빌드합니다.
# 명령을 실행할 때 Dockerfile 이 있는 디렉토리에 위치해야 합니다.
# 이미 pythonproject:3.12 가 존재하는 경우 이미지를 빌드할 필요가 없습니다.
docker build -t pythonproject:3.12 .

# 빌드한 이미지를 사용하여 Docker 컨테이너를 실행합니다.
docker run -itd --name web_socket_server -v <main.py 가 위치한 디렉토리 경로>:/opt/app -p 8000:8000 pythonproject:3.12 python main.py
```

# 웹 소켓 서버 접근 URL
```text
ws://localhost:8000/ws
```