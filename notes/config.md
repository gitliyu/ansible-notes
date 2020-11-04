### 环境配置
在运行Ansible命令时，命令将会按照以下顺序查找配置文件
- *ANSIBLE_CONFIG*：首先，检查环境变量及指向的配置文件
- *./ansible.cfg*：其次，检查当前⽬录下的ansible.cfg配置⽂件
- *~/.ansible.cfg*：再次，查当前⽤户根⽬录下的.ansible.cfg配置⽂件
- */etc/ansible/ansible.cfg*：最后，将会检查安装目录下的配置⽂件

大部分安装方式会直接创建`/etc/ansible/ansible.cfg`文件，但是比如`HomeBrew`安装时是没有的，需要自己创建

#### 配置参数
以下是`ansible.cfg`默认的几个配置参数和值
```
// inventory文件（即要管理的主机列表）位置
inventory = /etc/ansible/hosts
// 存放模块的目录
library = /usr/share/ansible/
// 进程并行处理的最大数量
forks = 5
// 使用sudo命令时默认的用户
sudo_user = root
// ssh默认端口
remote_port = 22
// 是否检查ssh主机密钥
host_key_checking = True
// 超时时间，单位是秒
timeout = 10
// 日志文件
log_path = /var/log/ansible.log
```
配置的详细参数和取值范围可以查看['ansible.cfg'](https://raw.github.com/ansible/ansible/devel/examples/ansible.cfg)

#### 环境变量设置
使用环境变量进行配置的话，以`sudo_user`为例
```
export ANSIBLE_SUDO_USER=root
```
以`ANSIBLE_`开头，参数大写的形式设置环境变量
