https://haengsin.tistory.com/128
```bash
ubuntu@myownserver:~$ sudo systemctl status docker
● docker.service - Docker Application Container Engine
     Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled)
     Active: active (running) since Tue 2023-12-19 10:16:10 UTC; 28s ago
TriggeredBy: ● docker.socket
       Docs: https://docs.docker.com
   Main PID: 3906 (dockerd)
      Tasks: 9
     Memory: 35.4M
     CGroup: /system.slice/docker.service
             └─3906 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock
```


```bash
ubuntu@myownserver:~$ docker pull ghcr.io/jackyzha0/quartz:hugo
permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Post "http://%2Fvar%2Frun%2Fdocker.sock/v1.24/images/create?fromImage=ghcr.io%2Fjackyzha0%2Fquartz&tag=hugo": dial unix /var/run/docker.sock: connect: permission denied
ubuntu@myownserver:~$ sudo docker pull ghcr.io/jackyzha0/quartz:hugo
hugo: Pulling from jackyzha0/quartz
c1d6d1b2d5a3: Pull complete 
4138ba036fba: Pull complete 
c8f3ec2c493c: Pull complete 
5d43a85b8281: Pull complete 
84ab9a838e80: Pull complete 
4f4fb700ef54: Pull complete 
Digest: sha256:0577760cf520e374c9daf712c9ced62236c7ecfe034139c57fcde98efaddf570
Status: Downloaded newer image for ghcr.io/jackyzha0/quartz:hugo
ghcr.io/jackyzha0/quartz:hugo
```

```bash
ubuntu@myownserver:~$ sudo groupadd docker
groupadd: group 'docker' already exists
ubuntu@myownserver:~$ sudo usermod -aG docker ${USER}
ubuntu@myownserver:~$ sudo systemctl restart docker
ubuntu@myownserver:~$ docker images
permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Get "http://%2Fvar%2Frun%2Fdocker.sock/v1.24/images/json": dial unix /var/run/docker.sock: connect: permission denied
ubuntu@myownserver:~$ sudo docker images
REPOSITORY                 TAG       IMAGE ID       CREATED        SIZE
ghcr.io/jackyzha0/quartz   hugo      73cd051f8748   4 months ago   656MB
ubuntu@myownserver:~$ sudo su -
root@myownserver:~# su - ubuntu
ubuntu@myownserver:~$ docker images
REPOSITORY                 TAG       IMAGE ID       CREATED        SIZE
ghcr.io/jackyzha0/quartz   hugo      73cd051f8748   4 months ago   656MB
```

https://velog.io/@jeong3320/dockerdocker-sudo%EA%B6%8C%ED%95%9C%EC%97%86%EC%9D%B4-%EC%8B%A4%ED%96%89%ED%95%98%EA%B8%B0