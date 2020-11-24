### 安装
`Ansible`可以在除Windows外的所有系统运行，安装方式有很多，这里介绍下几种不同系统较为方便的安装方式
#### MacOS
简单粗暴，使用`HomeBrew`直接安装
```
brew install ansible
```
#### Ubuntu
使用`apt`安装Ansible，只尝试过Ubuntu16.04和18.04
```
apt update

apt install software-properties-common

apt-add-repository --yes --update ppa:ansible/ansible

apt install ansible
```

#### CentOS
使用`yum`安装，由于Ansible软件默认不在标准仓库中，需要用到repo源
```
yum install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
yum install ansible -y
rpm -qa ansible
```
安装完成后可以执行`ansible --version`验证是否安装成功，更多安装方式可以查看['Ansible Installation Guide'](https://docs.ansible.com/ansible/latest/installation_guide/index.html)

