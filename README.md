# Linux 与 Shell 学习笔记

个人学习 Linux 与 Shell 的记录，涵盖常用命令、文件处理、脚本编写与自动化任务。内容以 Ubuntu/CentOS 为主。

## 仓库结构

| 文件 | 内容 |
|---|---|
| 01-common-commands.md | 常用命令（文件、进程、权限、网络） |
| 02-file-processing.md | 文本处理（grep / sed / awk / sort） |
| 03-shell-script.md | Shell 脚本编写与自动化 |

## 常用命令速查

```bash
# 文件与目录
ls -la          # 查看目录详情
cd /home/user   # 切换目录
cp -r dir1 dir2 # 复制目录
mv old new      # 移动/重命名
rm -rf dir      # 删除目录

# 权限
chmod 755 file.sh   # 修改权限
chown user:group f  # 修改所有者

# 进程
ps aux | grep java  # 查看进程
kill -9 PID         # 强制结束进程
top                 # 实时资源监控

# 网络
ping baidu.com          # 测试连通
curl -I https://x.com   # 查看响应头
ss -tlnp                # 查看端口占用
```

## 文本处理三板斧

```bash
grep 'error' app.log          # 过滤
sed -i 's/old/new/g' file.txt # 替换
awk '{print $1, $3}' data.txt # 取列
```

## 脚本自动化示例

```bash
#!/bin/bash
# 批量备份脚本
for f in *.txt; do
  cp "$f" "/backup/${f%.txt}_$(date +%Y%m%d).txt"
  done
  ```

  ## 后续计划
  - 定时任务 crontab
  - 环境变量与 PATH
  - 日志分析实战
  - Linux 面试高频题
  - 
