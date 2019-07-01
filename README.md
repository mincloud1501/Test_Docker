## 계정 만드세요.
http://dropbox.com
https://hub.docker.com
https://github.com


## Youtube 체널 : https://www.youtube.com/channel/UC2LdnDZduW6Qw_W18igE_Vg

## Devops Tools
Linux, bashShell, xen, kvm, OpenStack
Docker, Kubernetes, Rancher, Ansible, Terraform, Jenkins,

# Sublime Text
## 셋팅 방법 동영상
https://www.youtube.com/watch?v=ubPYAQJ-HjI
## Package control install
https://packagecontrol.io/installation

# Vagrant
1. Virtualbox를 설치하시오.
(Windows 10 Home 이하 유저는 Dockertoolbox 설치하면 Virtualbox 자동 설치됨) 
2. Vagrant를 설치하시오.
https://www.vagrantup.com/downloads.html 
3. 아래 스크립트를 통해 vagrant를 통해 Vm을 생성하시오.
```
cd
mkdir test
cd test/
vagrant init centos/7
vagrant up
vagrant ssh
```

## Examples
https://github.com/Finfra/vagrant-examples


## Vagrant Commnad
vagrant init vagrant박스명 ← 생략가능(Vagrantfile이 있으면)
vagrant up
vagrant status
vagrant ssh [node명]
vagrant halt
vagrant destroy
vagrant --help


# Docker
## Info
https://hub.docker.com

* docker toolbox사용자용.
```
docker-machine ip

```
## command Examples
```
docker search 키워드
docker run -it 이미지명
docker run -it --name 컨테이너명 이미지명
docker ps -a
docker attach
  ( ctl+p,q )
docker exec -it 컨테이너명 bash
docker stop
docker start
docker rm -f 컨테이너명
docker rmi 이미지명
docker run -d --name n1 -p 호스트포트:게스트포트 nginx
docker run -d --name n1 -v 호스트패쓰:게스트패쓰 nginx

docker commit -a "JungGu" -m "make xxx" n1 nginx:v1
docker save -o xx.docker 이미지명:tag
docker load -i xx.docker
```

## Image 선택
1. OFFICIAL
2. user이름이 없는 것.( nginx → OK, webdevops/nginx → 조심 )
3. Star높은 것
4. build script가 공개되어 있는 것.

## Docker run
* -it or -d
* --rm
* --name n1
* -p 8888:80
* -v /c/Users/GKN/df:/root/df

### nginx example
docker run -it --name n1 nginx
(다른창)
docker exec -it n1 bash
# cat /etc/*lease
# apt update -y
# apt install -y curl
# curl 127.0.0.1 or curl 192.168.99.100

### Docker Tip
```
# Container : Delete All
docker rm -f $(docker ps -a -q)
docker ps -a

# Image : Delete All
#for Window user
docker rmi $(docker images -q -f dangling=true)
#for MacOs user
docker rmi $(docker images|awk 'BEGIN{FS="\ {2,}"}FNR>1{printf "%s\n", $3}')
docker images

```


# Git
1. Gihub에서 Repository생성
2. Git clone to Push
```
   # Power Shell에서
   git clone https://github.com/Finfra/testDocker.git
   cd testDocker/
   cat .git/config
   echo "xxx" > README.md
   git add -A
   git config --global user.name "NamJungGu"
   git config --global user.email "nowage@gmail.com"
   git commit -m "first"
   git push
```
3. git pull
```
  git pull
```