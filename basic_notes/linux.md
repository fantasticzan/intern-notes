# linux命令



### 1. 文件与目录操作

```bash
cd 目录名            # 进入指定目录
cd ..                # 返回上一级目录
cd ~                 # 回到当前用户主目录
pwd                  # 显示当前所在目录
ls                   # 列出目录内容
ls -l                # 显示详细列表（权限、时间等）
ls -a                # 显示所有文件（含隐藏文件）
mkdir 目录名         # 创建新目录
mkdir -p 路径/目录   # 创建多级目录
rmdir 目录名         # 删除空目录
rm -r 目录名         # 删除目录及其内容
rm 文件名            # 删除文件
rm -f 文件名         # 强制删除
touch 文件名         # 创建空文件
cp 源 目标           # 复制文件
cp -r 源 目标目录     # 递归复制目录
mv 源 目标           # 移动文件或重命名
tree                 # 树状显示目录结构（需安装）
```

### 2. 文件查看与内容处理

```bash
cat 文件             # 显示文件内容（适合小文件）
tac 文件             # 反向显示内容
less 文件            # 分页查看（空格下一页，q退出）
more 文件            # 类似less
head -n 10 文件      # 显示前10行
tail -n 10 文件      # 显示后10行
tail -f 文件         # 实时查看文件内容（适用于日志）
wc -l 文件           # 查看文件行数
stat 文件            # 查看文件详细属性
file 文件            # 判断文件类型
cut -d':' -f1 /etc/passwd   # 提取指定字段
```

### 3. 权限管理与用户操作

```bash
ls -l 文件名         # 查看权限（drwxr-xr-x 结构）
chmod +x 文件        # 增加执行权限
chmod 755 文件       # 设置权限（rwxr-xr-x）
chown 用户 文件      # 修改文件所有者
chown 用户:组 文件   # 修改用户和组
adduser 用户名       # 添加用户
passwd 用户名        # 修改用户密码
su 用户名            # 切换用户
sudo 命令            # 以管理员权限执行命令
groups 用户名        # 查看用户所属组
usermod -aG 组 用户  # 添加用户到某个组
```

### 4. 查找与搜索

```bash
find / -name 文件名          # 查找文件
find . -type f -name "*.log" # 查找当前目录下的日志文件
locate 文件名                # 快速查找（需数据库）
updatedb                    # 更新locate数据库
grep "关键字" 文件           # 文件内容搜索
grep -rn "关键字" 路径       # 递归搜索并显示行号
grep -v "关键字" 文件        # 反向查找（不包含）
whereis 命令名               # 查找命令位置
which 命令名                 # 显示命令完整路径
```

### 5. 系统资源与性能查看

```bash
top                         # 实时查看系统资源使用
htop                        # 更强大的 top（需安装）
free -h                     # 查看内存占用
df -h                       # 查看磁盘使用情况
du -sh *                    # 查看当前目录下每个文件夹的大小
uptime                      # 查看系统运行时间
vmstat                      # 查看内存/IO信息
iostat                      # 查看磁盘性能（需安装）
lscpu                       # 查看CPU信息
lsblk                       # 查看磁盘分区
```

### 6. 网络相关命令

```bash
ping www.baidu.com          # 测试网络连接
curl http://地址            # 获取网页/接口数据
wget 链接地址               # 下载文件
ifconfig                    # 查看网络信息（老版本）
ip a                        # 新版查看IP地址
netstat -tulnp              # 查看端口监听（需安装）
ss -tuln                    # 查看端口连接状态
scp 文件 用户@IP:/目录       # 远程拷贝文件到服务器
ssh 用户@IP地址              # 远程登录
```

### 7. 软件安装与包管理（以Ubuntu/Debian为例）

```bash
sudo apt update              # 更新软件列表
sudo apt upgrade             # 升级所有软件
sudo apt install 软件名       # 安装软件
sudo apt remove 软件名        # 删除软件
dpkg -i 包名.deb             # 安装 .deb 软件包
dpkg -l                     # 查看已安装软件
```

### 8. 打包与压缩

```bash
tar -czvf 压缩包.tar.gz 目录    # 压缩
tar -xzvf 压缩包.tar.gz         # 解压
zip -r 包名.zip 目录            # 压缩为zip
unzip 包名.zip                  # 解压zip
gzip 文件名                    # 压缩为.gz
gunzip 文件.gz                 # 解压.gz
```

### 9. 进程与服务管理

```bash
ps aux                       # 查看所有进程
ps -ef | grep xxx            # 查找进程
kill PID                     # 杀死进程
kill -9 PID                  # 强制杀死
pkill 名称                   # 按名称杀死进程
systemctl status 服务名      # 查看服务状态
systemctl start 服务名       # 启动服务
systemctl stop 服务名        # 停止服务
systemctl restart 服务名     # 重启服务
systemctl enable 服务名      # 设置开机启动
systemctl disable 服务名     # 禁用开机启动
```

### 10. 其他实用命令

```bash
history                      # 显示历史命令
clear                        # 清屏
alias ll='ls -l'             # 设置别名
date                         # 显示当前时间
cal                          # 显示日历
reboot                       # 重启系统
shutdown -h now              # 立即关机
shutdown -r +5               # 5分钟后重启
```