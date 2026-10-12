# 03 Shell 脚本编写与自动化

## 1. 脚本基础结构

```bash
#!/bin/bash
# 注释：脚本作用
echo "Hello, World"
```

运行方式：
```bash
chmod +x run.sh   # 加执行权限
./run.sh          # 直接运行
bash run.sh       # 或用 bash 运行
```

## 2. 变量

```bash
# 定义变量（等号两边不能有空格）
name="QIAO"
age=20

# 使用变量
echo "名字: $name"
echo "年龄: ${age}"

# 命令结果存变量
files=$(ls)
echo "$files"
```

## 3. 条件判断

```bash
if [ -f "file.txt" ]; then
  echo "文件存在"
  elif [ -d "dir" ]; then
    echo "目录存在"
    else
      echo "都不存在"
      fi

      # 常用判断
      [ "$a" = "$b" ]    # 字符串相等
      [ "$a" != "$b" ]   # 字符串不等
      [ $num -gt 100 ]   # 数字大于
      [ -f file ]        # 是文件
      [ -d dir ]         # 是目录
      ```

      ## 4. 循环

      ```bash
      # for 循环
      for i in 1 2 3 4 5; do
        echo "第 $i 次"
        done

        # 遍历文件
        for f in *.txt; do
          echo "处理 $f"
          done

          # while 循环
          count=1
          while [ $count -le 5 ]; do
            echo $count
              count=$((count + 1))
              done
              ```

              ## 5. 实战：批量备份脚本

              ```bash
              #!/bin/bash
              # 批量备份 .txt 文件，文件名加日期
              backup_dir="/backup/$(date +%Y%m%d)"
              mkdir -p "$backup_dir"

              for f in *.txt; do
                cp "$f" "$backup_dir/${f%.txt}_$(date +%Y%m%d).txt"
                  echo "已备份: $f"
                  done

                  echo "备份完成，共 $(ls $backup_dir | wc -l) 个文件"
                  ```

                  ## 6. 实战：检查磁盘空间并报警

                  ```bash
                  #!/bin/bash
                  # 磁盘使用率超过 80% 报警
                  usage=$(df -h / | awk 'NR==2 {print $5}' | tr -d '%')

                  if [ $usage -gt 80 ]; then
                    echo "警告：磁盘使用率已达 $usage%"
                    else
                      echo "磁盘正常：使用率 $usage%"
                      fi
                      ```
