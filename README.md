# usdtbillmon
 trc20 usdt bill monitor
 
#安装docker

apt update

apt install curl vim wget gnupg dpkg apt-transport-https lsb-release ca-certificates

curl -sS https://download.docker.com/linux/debian/gpg | gpg --dearmor > /usr/share/keyrings/docker-ce.gpg

echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-ce.gpg] https://download.docker.com/linux/debian $(lsb_release -sc) stable" > /etc/apt/sources.list.d/docker.list

apt update

apt-get install docker-ce docker-ce-cli containerd.io

systemctl enable docker

systemctl start docker

sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose


把部署目录clone 下来


git clone https://github.com/zhongziso/usdtbillmon.git

如果没有装git ，请 yum -y install git 安装

# 添加你的 key

你最终要准备的目录内容是这样的

```
├── docker-compose.yml
├── env.conf
├── key.data
├── mysql_init
│   └── ct_table.sql
└── redis.conf
```


你需要修改  

key.data 文件内容为你的机器人的 key （第一步获取的）

# 运行docker

docker-compose up -d

成功运行

# 添加机器人

/start  开始接收收款监听


修改了一些bug：
 
- 同一秒有问题的bug



