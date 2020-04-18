# Note  
## 通过修改hosts文件解决github无法加载用户头像及raw文件的问题  
在hosts文件末尾追加以下IP地址： 
  
> \# GitHub  
151.101.108.133 camo.githubusercontent.com  
151.101.108.133 avatars0.githubusercontent.com  
151.101.108.133 avatars1.githubusercontent.com  
151.101.108.133 avatars2.githubusercontent.com  
151.101.108.133 avatars3.githubusercontent.com  
151.101.76.133 raw.githubusercontent.com  



## Ubuntu搭建运行PHP文件的环境
### 总体步骤：
1. 安装apache2
2. 安装MySQL
3. 安装PHP

### 详细步骤：
#### 1. 安装apache2：
``` bash
apt install apache2    //输入Y同意
//检查是否安装成功： 在浏览器内输入 http:localhost
//若显示 Apache2 Ubuntu Default Page ，则表明已安装成功
```
#### 2. 安装MySQL：
``` bash
apt install mysql-server
apt install mysql-client
apt install libmysqlclient-dev
//继续安装net-tools：
apt install net-tools
//检查是否安装成功：
sudo netstat -tap | grep mysql
//若mysql的socket处于listen状态则表示安装成功
```
#### 3. 安装PHP：
``` bash
sudo apt install php    //输入Y同意
//查询适合的PHP插件
sudo apt-cache search libapache2-mod-php 
//安装插件 
sudo apt install libapache2-mod-php*   //*为查询到的版本
//将.php文件放入 /var/www/html 文件夹中
//在浏览器中输入127.0.0.1/*.php   //*.php为想打开的PHP文件
```
