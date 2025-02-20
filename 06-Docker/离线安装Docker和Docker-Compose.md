```
# step 01
download from https://download.docker.com/linux/static/stable/x86_64/


# step 02
tar xvf docker-27.5.0.tgz


# step 03
sudo cp ./docker/* /usr/bin/


# step 04
vim /etc/systemd/system/docker.service
[Unit]
Description=Docker Application Container Engine
Documentation=https://docs.docker.com
After=network-online.target firewalld.service
Wants=network-online.target

[Service]
Type=notify
ExecStart=/usr/bin/dockerd
ExecReload=/bin/kill -s HUP $MAINPID
LimitNOFILE=infinity
LimitNPROC=infinity
TimeoutStartSec=0
Delegate=yes
KillMode=process
Restart=on-failure
StartLimitBurst=3
StartLimitInterval=60s

[Install]
WantedBy=multi-user.target


# step 05
sudo chmod +x /etc/systemd/system/docker.service
sudo systemctl daemon-reload
sudo systemctl enable docker.service
sudo systemctl start docker


# step 06
docker -v


# step 07
download from https://github.com/docker/compose/releases


# step 08
sudo cp docker-compose-linux-x86_64 /usr/local/bin/docker-compose


# step 09
sudo chmod u+x /usr/local/bin/docker-compose


# step 10
docker-compose -v


Reference:
https://blog.csdn.net/weixin_42571882/article/details/134015815
https://blog.csdn.net/qq_30779089/article/details/125535417
```