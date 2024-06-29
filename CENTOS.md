# CentOS

### 升级Yum
```
sudo yum update

sudo yum install -y gcc
```

### 安装PIP
```
yum -y install epel-release

yum -y install python-pip

pip install --upgrade pip
```

### 安装Docker
```
yum install docker
```

### Docker-Compose安装方式1-第1步：安装Python3和PIP3
```
yum install zlib-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel tk-devel gcc make

wget https://www.python.org/ftp/python/3.6.2/Python-3.6.2.tar.xz

tar -xvJf Python-3.6.2.tar.xz
cd Python-3.6.2

./configure prefix=/usr/local/python3
make && make install

ln -s /usr/local/python3/bin/python3 /usr/bin/python3
ln -s /usr/local/python3/bin/pip3 /usr/bin/pip3

pip3 install --upgrade pip
```

### Docker-Compose安装方式1-第2步：安装Docker-Compose
```
sudo pip3 install docker-compose
或
sudo pip3 install docker-compose --ignore-installed requests

docker-compose --version
```

### Docker-Compose安装方式2-二进制：安装Docker-Compose
```
sudo curl -L https://github.com/docker/compose/releases/download/1.27.4/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose

chmod +x /usr/local/bin/docker-compose

docker-compose --version
```

### 安装Git
```
yum install -y git

git config --global credential.helper store
```

### 配置镜像
```
sudo mkdir -p /etc/docker
sudo tee /etc/docker/daemon.json <<-'EOF'
{
  "registry-mirrors": ["https://nb9lqh8t.mirror.aliyuncs.com"]
}
EOF
sudo systemctl daemon-reload
sudo systemctl restart docker
```
