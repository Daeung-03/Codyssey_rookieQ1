## 1. 설치 및 확인
hugeung@gimdaeung-ui-MacBookAir Codyssey1st_rookie % docker --version   
Docker version 29.2.1, build a5c7197   
hugeung@gimdaeung-ui-MacBookAir Codyssey1st_rookie % docker info   
Client:   
 Version:    29.2.1   
 Context:    desktop-linux   
 Debug Mode: false    
 Plugins:   
  agent: create or run AI agents (Docker Inc.)   
    Version:  v1.27.1   
    Path:     /Users/hugeung/.docker/cli-plugins/docker-agent   
  ai: Docker AI Agent - Ask Gordon (Docker Inc.)   
    Version:  v1.18.0   
    Path:     /Users/hugeung/.docker/cli-plugins/docker-ai    
  buildx: Docker Buildx (Docker Inc.)    
    Version:  v0.31.1-desktop.1   
    Path:     /Users/hugeung/.docker/cli-plugins/docker-buildx     
  compose: Docker Compose (Docker Inc.)   
    Version:  v5.0.2   
    Path:     /Users/hugeung/.docker/cli-plugins/docker-compose    
  debug: Get a shell into any image or container (Docker Inc.)   
    Version:  0.0.47    
    Path:     /Users/hugeung/.docker/cli-plugins/docker-debug   
  desktop: Docker Desktop commands (Docker Inc.)   
    Version:  v0.3.0    
    Path:     /Users/hugeung/.docker/cli-plugins/docker-desktop   
  extension: Manages Docker extensions (Docker Inc.)   
    Version:  v0.2.31   
    Path:     /Users/hugeung/.docker/cli-plugins/docker-extension
  init: Creates Docker-related starter files for your project (Docker Inc.)
    Version:  v1.4.0
    Path:     /Users/hugeung/.docker/cli-plugins/docker-init
  mcp: Docker MCP Plugin (Docker Inc.)
    Version:  v0.40.1
    Path:     /Users/hugeung/.docker/cli-plugins/docker-mcp
  model: Docker Model Runner (Docker Inc.)
    Version:  v1.1.1
    Path:     /Users/hugeung/.docker/cli-plugins/docker-model
  offload: Docker Offload (Docker Inc.)
    Version:  v0.5.56
    Path:     /Users/hugeung/.docker/cli-plugins/docker-offload
  pass: Docker Pass Secrets Manager Plugin (beta) (Docker Inc.)
    Version:  v0.0.24
    Path:     /Users/hugeung/.docker/cli-plugins/docker-pass
  sandbox: Docker Sandbox (Docker Inc.)
    Version:  v0.12.0
    Path:     /Users/hugeung/.docker/cli-plugins/docker-sandbox
  sbom: View the packaged-based Software Bill Of Materials (SBOM) for an image (Anchore Inc.)
    Version:  0.6.0
    Path:     /Users/hugeung/.docker/cli-plugins/docker-sbom
  scout: Docker Scout (Docker Inc.)
    Version:  v1.20.0
    Path:     /Users/hugeung/.docker/cli-plugins/docker-scout

Server:
 Containers: 1
  Running: 0
  Paused: 0
  Stopped: 1
 Images: 2
 Server Version: 29.2.1
 Storage Driver: overlayfs
  driver-type: io.containerd.snapshotter.v1
 Logging Driver: json-file
 Cgroup Driver: cgroupfs
 Cgroup Version: 2
 Plugins:
  Volume: local
  Network: bridge host ipvlan macvlan null overlay
  Log: awslogs fluentd gcplogs gelf journald json-file local splunk syslog
 CDI spec directories:
  /etc/cdi
  /var/run/cdi
 Discovered Devices:
  cdi: docker.com/gpu=webgpu
 Swarm: inactive
 Runtimes: io.containerd.runc.v2 runc
 Default Runtime: runc
 Init Binary: docker-init
 containerd version: dea7da592f5d1d2b7755e3a161be07f43fad8f75
 runc version: v1.3.4-0-gd6d73eb8
 init version: de40ad0
 Security Options:
  seccomp
   Profile: builtin
  cgroupns
 Kernel Version: 6.12.72-linuxkit
 Operating System: Docker Desktop
 OSType: linux
 Architecture: aarch64
 CPUs: 10
 Total Memory: 7.653GiB
 Name: docker-desktop
 ID: b60b1195-78e5-414f-8b23-9273760b6fd5
 Docker Root Dir: /var/lib/docker
 Debug Mode: false
 HTTP Proxy: http.docker.internal:3128
 HTTPS Proxy: http.docker.internal:3128
 No Proxy: hubproxy.docker.internal
 Labels:
  com.docker.desktop.address=unix:///Users/hugeung/Library/Containers/com.docker.docker/Data/docker-cli.sock
 Experimental: false
 Insecure Registries:
  hubproxy.docker.internal:5555
  ::1/128
  127.0.0.0/8
 Live Restore Enabled: false
 Firewall Backend: iptables

## 2. docker 간단한 조작
hugeung@gimdaeung-ui-MacBookAir Codyssey1st_rookie % docker images
                                                                                             i Info →   U  In Use
IMAGE                             ID             DISK USAGE   CONTENT SIZE   EXTRA
docker/welcome-to-docker:latest   c4d56c24da4f       22.9MB         6.35MB        
hello-world:latest                85404b3c5395       22.5kB         10.2kB    U   
ubuntu:latest                     186072bba1b2        141MB         30.8MB    U   
hugeung@gimdaeung-ui-MacBookAir Codyssey1st_rookie % docker pull hello-world
Using default tag: latest
latest: Pulling from library/hello-world
58dee6a49ef1: Pull complete 
c3bdf82c34d1: Download complete 
Digest: sha256:452a468a4bf985040037cb6d5392410206e47db9bf5b7278d281f94d1c2d0931
Status: Downloaded newer image for hello-world:latest
docker.io/library/hello-world:latest
hugeung@gimdaeung-ui-MacBookAir Codyssey1st_rookie % docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
hugeung@gimdaeung-ui-MacBookAir Codyssey1st_rookie % docker ps -a
CONTAINER ID   IMAGE          COMMAND    CREATED         STATUS                      PORTS     NAMES
ab0839e389dc   ubuntu         "bash"     4 minutes ago   Exited (0) 52 seconds ago             laughing_sinoussi
8defa3a2e456   85404b3c5395   "/hello"   5 minutes ago   Exited (0) 5 minutes ago              flamboyant_darwin
bc6adc0b5d0c   85404b3c5395   "/hello"   3 weeks ago     Exited (0) 3 weeks ago                blissful_mahavira
hugeung@gimdaeung-ui-MacBookAir Codyssey1st_rookie % docker logs 8defa3a2e456

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (arm64v8)
 3. The Docker daemon created a new container from that image which runs the

## 3. 컨테이너 실행 실습(attach vs exec)
hugeung@gimdaeung-ui-MacBookAir Codyssey1st_rookie % docker run -it ubuntu bash
root@c5441f7400fe:/# ls   
bin  boot  dev  etc  home  lib  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
root@c5441f7400fe:/# ehco "inside"
bash: ehco: command not found
root@c5441f7400fe:/# echo "inside"
inside
root@c5441f7400fe:/# 
(other terminal)
hugeung@gimdaeung-ui-MacBookAir ~ % docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED          STATUS          PORTS     NAMES
c5441f7400fe   ubuntu    "bash"    31 seconds ago   Up 30 seconds             mystifying_shamir
hugeung@gimdaeung-ui-MacBookAir ~ % docker exec -it mystifying_shamir          
docker: 'docker exec' requires at least 2 arguments

Usage:  docker exec [OPTIONS] CONTAINER COMMAND [ARG...]

See 'docker exec --help' for more information
hugeung@gimdaeung-ui-MacBookAir ~ % docker exec -it mystifying_shamir bash
root@c5441f7400fe:/# exit
exit
hugeung@gimdaeung-ui-MacBookAir ~ % docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED              STATUS              PORTS     NAMES
c5441f7400fe   ubuntu    "bash"    About a minute ago   Up About a minute             mystifying_shamir

hugeung@gimdaeung-ui-MacBookAir ~ % docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED         STATUS         PORTS     NAMES
efb0e6b9ac99   ubuntu    "bash"    5 seconds ago   Up 4 seconds             xenodochial_villani
hugeung@gimdaeung-ui-MacBookAir ~ % docker attach xenodochial_villani
root@efb0e6b9ac99:/# 
exit
hugeung@gimdaeung-ui-MacBookAir ~ % docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES

ugeung@gimdaeung-ui-MacBookAir Codyssey1st_rookie % docker run -dit --name mybox ubuntu /bin/bash
57c8628f907263e3066bc038d4f4f2b41e586766e5789efa6580471bab46813e
hugeung@gimdaeung-ui-MacBookAir Codyssey1st_rookie % docker top mybox
UID                 PID                 PPID                C                   STIME               TTY                 TIME                CMD
root                938                 914                 0                   08:36               ?                   00:00:00            /bin/bash
hugeung@gimdaeung-ui-MacBookAir Codyssey1st_rookie % docker exec -it mybox /bin/bash
root@57c8628f9072:/# ps aux
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root         1  0.0  0.0   4300  3604 pts/0    Ss+  08:36   0:00 /bin/bash
root         9  0.0  0.0   4300  3632 pts/1    Ss   08:37   0:00 /bin/bash
root        17  0.0  0.0   7632  3656 pts/1    R+   08:37   0:00 ps aux
root@57c8628f9072:/# exit
exit
hugeung@gimdaeung-ui-MacBookAir Codyssey1st_rookie % docker attach mybox
root@57c8628f9072:/# ps aux
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root         1  0.0  0.0   4300  3612 pts/0    Ss   08:36   0:00 /bin/bash
root        18  0.0  0.0   7632  3656 pts/0    R+   08:37   0:00 ps aux

위 로그에서 확인할 수 있듯이 attach는 지금 메인스트림(실행중인 컨테이너)를 내 터미널로 바꾸는 것, exec 보조 프로세스를 생성하는 것이다. 따라서 종료 시에 차이가 있음.