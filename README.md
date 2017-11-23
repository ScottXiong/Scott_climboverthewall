### purchase via [vultr](https://my.vultr.com/deploy/)
- server location :seattle
- server type :64bit os([centos](http://blog.csdn.net/lilong_dream/article/details/17081067) 7x64)
- server size :choose USD5 per month
- Additional Features
  <ul>
		<li>Enable IPv6</li>
		<li>Enable Private Network</li>
	</ul>
- Server Hostname & Label:just your ip name
- deploy now:click then you will get one ip adress distributed by the service, what we will do next is just to open the terminal and ping it. If it less than 300ms, it will be OK then we choose it, otherwise we should repeart the action until
we get the best one.
<hr>

### login via terminal
```
ssh root@ip
password
//sucessful notification:There was 1 failed login attempt since the last successful login.
Last login: Thu Nov 23 08:04:39 2017 from 113.102.242.252
python版的安装方式如下
在ssh软件中复制粘贴下面的代码，并回车
yum update -y
yum install python python-pip vim supervisor -y
pip install shadsowsocks
systemctl enable supervisord
完成后输入 vim /etc/shadowsocks/config.json 回车
输入 i ，粘贴一下内容

{
 "server":"your ip",
 "local_port":1080,
 "local_address":"127.0.0.1",
 "port_password":{
   "1st port":"password",
   "second port":"password"
  },
 "timeout":600,
 "method":"你的加密方式",
 "mode":"tcp_and_udp",
 "fast_open":true
}
完成后按esc，输入：wq 回车
完成后输入 nohup ssserver -c /etc/shadowsocks/config.json &回车
现在退出ssh，可以连接ss了
```
