+++
title = 'Jarvis'
date = 2023-11-08T18:08:48+09:00
draft = true
+++
## J.A.R.V.I.S

### Docker 개발환경

#### [Host] docker cli
* 설치    
```Bash
    brew install docker
```

#### [GuestVM] linux docker engine (community edition)
* [lima](https://github.com/lima-vm/lima) 설치
```Bash
    brew install lima
    limactl --version
    # limactl version 0.18.0
```

* Docker Engine CE가 설치된 Ubuntu VM 설정파일 다운로드
```Bash
    wget https://raw.githubusercontent.com/lima-vm/lima/master/examples/docker.yaml
    cat ./docker.yaml
```

* lima docker.yaml 파일 기반의 VM 생성
```Bash
    limactl start ./docker.yaml
```

* 생성한 VM 조회 (VM명은 파일명 그대로 docker)
```Bash
    limactl list

    #NAME      STATUS     SSH                VMTYPE    ARCH       CPUS    MEMORY    DISK      DIR
    #docker    Running    127.0.0.1:52904    qemu      aarch64    4       4GiB      100GiB    ~/.lima/docker
```

* docker VM에 ssh 접속 / 명령어 전달
```Bash
    # limactl shell ${INSTANCE} [COMMAND...]
    limactl shell docker # 접속
    limactl shell docker ls -al # 명령어 전달
```

* VM과 ${HOME} 디렉토리를 공유하는지 확인
```Bash
    ls /Users
    limactl shell docker /Users
```

* VM 외부에서 호스트 docker cli를 연결
```Bash
    export DOCKER_HOST=$(limactl list docker --format 'unix://{{.Dir}}/sock/docker.sock')
    docker info
        # lima-docker인지 확인
        Operating System: Ubuntu 22.04.3 LTS
        OSType: linux
        Architecture: aarch64
        CPUs: 4
        Total Memory: 3.819GiB
        Name: lima-docker
        Docker Root Dir: /home/byungkwonc.linux/.local/share/docker

    docker run hello-world
        # Hello from Docker!
```

* 생성한 VM 중지 및 삭제
```Bash
    limactl stop docker
    limactl delete docker
```

### OrbStack

#### Download
* [Download OrbStack](https://orbstack.dev/download) and open it, no installation needed.

#### Homebrew
```Bash
    brew install orbstack
```