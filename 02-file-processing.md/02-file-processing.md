# 02 文件处理与文本分析

## 1. grep 过滤

```bash
grep 'error' app.log              # 找包含 error 的行
grep -i 'error' app.log           # 忽略大小写
grep -v 'debug' app.log           # 排除 debug
grep -c 'error' app.log           # 统计行数
grep -r 'TODO' src/               # 递归搜索目录
```

## 2. sed 替换

```bash
sed 's/old/new/' file.txt         # 每行第一个替换
sed 's/old/new/g' file.txt        # 全部替换
sed -i 's/old/new/g' file.txt     # 直接修改文件
sed -n '5,10p' file.txt           # 打印第5-10行
```

## 3. awk 取列

```bash
awk '{print $1, $3}' data.txt     # 取第1、3列
awk -F',' '{print $2}' data.csv   # 按逗号分割取第2列
awk '$3 > 100' data.txt           # 条件过滤
awk '{sum += $2} END {print sum}' data.txt  # 求和
```

## 4. 排序与去重

```bash
sort file.txt                     # 排序
sort -n file.txt                  # 按数字排序
sort -r file.txt                  # 倒序
uniq -c file.txt                  # 去重并计数
sort file.txt | uniq -c | sort -rn   # 词频统计经典组合
```

## 5. 实战：日志分析

```bash
# 统计访问次数 Top 10 的 IP
awk '{print $1}' access.log | sort | uniq -c | sort -rn | head -10

# 统计某时间段错误数
grep '2026-10-01' app.log | grep -c 'ERROR'
```
