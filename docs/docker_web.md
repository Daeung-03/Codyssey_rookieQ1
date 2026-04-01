## 1. Dockerfile 작성 및 빌드
FROM 베이스이미지
LABEL 메타데이터
WORKDIR 컨테이너 내부 디렉토리
RUN 이미지 빌드 시 실행할 명령어 

hugeung@gimdaeung-ui-MacBookAir my_webserver % docker build -t my-webserver:1.0 .
[+] Building 6.9s (10/10) FINISHED                                                                           docker:desktop-linux
 => [internal] load build definition from Dockerfile                                                                         0.0s
 => => transferring dockerfile: 1.13kB                                                                                       0.0s
 => [internal] load metadata for docker.io/library/nginx:stable-alpine                                                       3.4s
 => [auth] library/nginx:pull token for registry-1.docker.io                                                                 0.0s
 => [internal] load .dockerignore                                                                                            0.0s
 => => transferring context: 2B                                                                                              0.0s
 => [1/4] FROM docker.io/library/nginx:stable-alpine@sha256:a8b39bd9cf0f83869a2162827a0caf6137ddf759d50a171451b335cecc87d23  3.0s
 => => resolve docker.io/library/nginx:stable-alpine@sha256:a8b39bd9cf0f83869a2162827a0caf6137ddf759d50a171451b335cecc87d23  0.0s
 => => sha256:40b38cc61f0ed9f05cc4513445f27d89576e409b87c570c10407be8f17811fcd 19.72MB / 19.72MB                             2.3s
 => => sha256:04e73639757d2fe4a5fa6e1c03b2eaf6de521cfb97433e57fbca027d787d57f3 1.40kB / 1.40kB                               0.9s
 => => sha256:004928619bd7ca6c2d3092673b3e08e40d8603df0a1d604a13228ff8f4c3a969 1.21kB / 1.21kB                               1.1s
 => => sha256:3d2c901b120a3a0488cc5bf5b6c9f739a3fbaabbb8b0238fddc99fe40b5c1790 953B / 953B                                   1.1s
 => => sha256:39ba19c6a1e3b8a62dce91cb78eb6b4344fc81833da73cecbf0e34fa8c5d0e71 402B / 402B                                   0.8s
 => => sha256:0190f85b656602c295783e3e0b93423890316e896a1bba05d1ab48da0e23bb43 1.85MB / 1.85MB                               1.1s
 => => sha256:0c9e85b345e6064c61d3655ec4390c0d13d45d8becbd25c5a7ac3db8b4097cfd 625B / 625B                                   0.8s
 => => sha256:d8ad8cd72600f46cc068e16c39046ebc76526e41051f43a8c249884b200936c0 4.20MB / 4.20MB                               0.8s
 => => extracting sha256:d8ad8cd72600f46cc068e16c39046ebc76526e41051f43a8c249884b200936c0                                    0.1s
 => => extracting sha256:0190f85b656602c295783e3e0b93423890316e896a1bba05d1ab48da0e23bb43                                    0.1s
 => => extracting sha256:0c9e85b345e6064c61d3655ec4390c0d13d45d8becbd25c5a7ac3db8b4097cfd                                    0.0s
 => => extracting sha256:3d2c901b120a3a0488cc5bf5b6c9f739a3fbaabbb8b0238fddc99fe40b5c1790                                    0.0s
 => => extracting sha256:39ba19c6a1e3b8a62dce91cb78eb6b4344fc81833da73cecbf0e34fa8c5d0e71                                    0.0s
 => => extracting sha256:004928619bd7ca6c2d3092673b3e08e40d8603df0a1d604a13228ff8f4c3a969                                    0.0s
 => => extracting sha256:04e73639757d2fe4a5fa6e1c03b2eaf6de521cfb97433e57fbca027d787d57f3                                    0.0s
 => => extracting sha256:40b38cc61f0ed9f05cc4513445f27d89576e409b87c570c10407be8f17811fcd                                    0.3s
 => [internal] load build context                                                                                            0.0s
 => => transferring context: 220B                                                                                            0.0s
 => [2/4] WORKDIR /usr/share/nginx/html                                                                                      0.1s
 => [3/4] RUN rm -f /usr/share/nginx/html/* || true                                                                          0.2s
 => [4/4] COPY index.html /usr/share/nginx/html/index.html                                                                   0.0s
 => exporting to image                                                                                                       0.1s
 => => exporting layers                                                                                                      0.0s
 => => exporting manifest sha256:7ad4c35c8e3f0669913af87f48966cb70b01d33dd80c31bbd5a68c2ec55a654c                            0.0s
 => => exporting config sha256:3ca9f580945d577ff4ae6ff59ff43091d1e158e9c3e1de2860822866f6c00e6d                              0.0s
 => => exporting attestation manifest sha256:8e46eeae158e169055e9a1026980ad7dc29dd8376b8d46b42ac9b782c24a3751                0.0s
 => => exporting manifest list sha256:0e23999027c9d4e4c7db9692b490e5c41bfc058e1c8fda8f64a37c4e2072575f                       0.0s
 => => naming to docker.io/library/my-webserver:1.0                                                                          0.0s
 => => unpacking to docker.io/library/my-webserver:1.0    

## 2. 포트포워딩
hugeung@gimdaeung-ui-MacBookAir ~ % docker run -d -p 8080:80 --name web-test1 my-webserver:1.0
2533ec825f4a07fd91983dd52404bb4cdf90a6982988146175c38245c7ab4c64

컨테이너는 격리된 네트워크 안에 있어서, 외부(호스트)에서 접근하려면 호스트 포트와 컨테이너 포트를 연결(매핑) 해줘야 합니다.
-p 옵션으로 가능 