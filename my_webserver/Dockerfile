# 베이스 이미지: 공식 NGINX (alpine 기반으로 가볍고 실습에 적합)
FROM nginx:stable-alpine

# 메타데이터(선택이지만, 이미지 관리/추적에 유용)
LABEL org.opencontainers.image.title="my_webserver"
LABEL org.opencontainers.image.description="Static index.html served by NGINX (for port forwarding practice)"
LABEL org.opencontainers.image.source="Codyssey1st_rookie/my_webserver"

# 컨테이너 내부 작업 디렉토리(필수는 아니지만 명시)
WORKDIR /usr/share/nginx/html

# 기본으로 들어있는 welcome 페이지를 지우고(선택),
# 우리 index.html을 NGINX 기본 웹루트로 복사
RUN rm -f /usr/share/nginx/html/* || true
COPY index.html /usr/share/nginx/html/index.html

# (선택) 정적 파일 캐시/갱신 실습 시 편의. 필요 없으면 제거해도 됨.
# 컨테이너 환경변수로 버전/빌드정보를 남겨두면 확인하기 좋음.
ENV APP_NAME="my_webserver" \
    APP_ENV="docker" \
    TZ="Asia/Seoul"

# NGINX 기본 리스닝 포트(컨테이너 내부 포트)
EXPOSE 80

# 컨테이너는 PID 1 프로세스가 살아있어야 유지됨.
# nginx를 포그라운드(daemon off)로 실행해야 컨테이너가 종료되지 않는다.
CMD ["nginx", "-g", "daemon off;"]
