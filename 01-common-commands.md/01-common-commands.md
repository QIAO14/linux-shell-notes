# 01 常用命令

## 1. 文件与目录

```bash
pwd                 # 当前路径
ls -la              # 查看目录详情（含隐藏文件）
cd /home/user       # 切换目录
mkdir -p a/b/c      # 递归创建目录
cp -r dir1 dir2     # 复制目录
mv old new          # 移动/重命名
rm -rf dir          # 删除目录（慎用）
touch file.txt      # 创建空文件
```

## 2. 权限管理

```bash
chmod 755 file.sh   # 修改权限（rwxr-xr-x）
chmod +x run.sh     # 加执行权限
chown user:group f  # 修改所有者
```

权限数字：r=4, w=2, x=1

| 数字 | 权限 |
|---|---|
| 7 | rwx 读写执行 |
| 6 | rw- 读写 |
| 5 | r-x 读执行 |
| 4 | r-- 只读 |

## 3. 进程管理

```bash
ps aux              # 查看所有进程
ps aux | grep java  # 过滤进程
kill -9 PID         # 强制结束
top                 # 实时监控（q 退出）
nohup cmd &         # 后台运行
```

## 4. 网络

```bash
ping baidu.com          # 测试连通
curl -I https://x.com   # 查看响应头
curl -o file url        # 下载文件
ss -tlnp                # 查看端口占用
ifconfig / ip addr      # 查看网卡
```

## 5. 磁盘与内存

```bash
df -h               # 磁盘空间
du -sh /var/log     # 目录大小
free -h             # 内存情况
```

## 6. 压缩与解压

```bash
tar -czvf a.tar.gz dir/   # 打包压缩
tar -xzvf a.tar.gz        # 解压
unzip a.zip               # 解压zip
```
