本文记一些常用的网络命令，包括write、ping、ifconfig、last、traceroute、netstat等命令。

### write命令

**write 用户名：**给指定在线用户发送信息，回车后就可以编辑需要发送的信息，编辑信息完信息后以Ctrl+D或Ctrl+c保存结束并发送（最好是在新的一行保存发送）。

**wall 信息：**给所有在线用户发送信息，即广播，包括自己也会收到信息。

**注意：  
**

* 写信息时，可以使用delete键或Ctrl+退格键进行删除操作。
* 收到信息时，信息末尾的EOF是默认的结束标识。

### ping命令

**ping \[选项\] IP：**和Windows一样，都是用于测试网络连通性，但不同的是，如果不加选项，直接ping，那么Linux会不停的发送请求，直到Ctrl+C结束。而Windows默认只会发送四次。注意，ping本机的时候，一定不要ping127.0.0.1，而是ping自己的ip地址。

**选项：**

* **-c：**指定发送次数。如ping -c 3 192.168.8.250。

### ifconfig命令

**ifconfig \[网卡名称\] \[IP\]：**查看和设置网卡信息，相当于Windows的ipconfig（与Linux只差一个字母）。如ifconfig eth0 192.168.8.250。直接输入ifconfig则表示查看所有网卡信息。

**网卡信息常用项：  
**

* **Link encap：**网络类型，一般就是以太网Ethernet。
* **HWaddr：**网卡的MAC地址，即网卡的物理地址。
* **inet addr：**当前网卡的ip地址。

### last命令

**last：**列出过去和目前的登录用户信息，包括重启操作也会显示出来。

**lastlog：**列出所有用户的最后一次登录信息（未登录过的用户也会列出来）。

**lastlog -u 用户id：**只看某个用户的最后一次登录信息。

### traceroute命令

**traceroute 网址：**显示数据包到达主机之间的节点路径。更多选项参数可自行查看。

### netstat命令

**netstat \[选项\]：**显示网络相关信息。

**选项：  
**

* **-t：**TCP协议。
* **-u：**UDP协议。
* **-l：**监听，查看监听的端口。
* **-r：**路由，查看网关信息。
* **-n：**显示ip地址和端口号。

**常用示例：  
**

* **netstat -tlun：**查看本机监听的端口。
* **netstat -an：**查看本机所有的网络连接，包括监听的和正在连接的端口，以及正在使用端口的程序。注意，程序发起端口都是随机的，而接收的端口却是固定的。
* **netstat -tlun：**查看本机路由表。


