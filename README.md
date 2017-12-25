# LINUX 常用命令
## 系统
### 切换root用户
`sudo -i`
## systemctl

## 文件
### 新建文件
* `touch fileName`
* `vi fileName`
### 查看文件内容
`cat fileName`
### 清空文件内容
* `$ : > filename `
* `$ > filename `
* `$ echo "" > filename `
* `$ echo > filename `
* `$ cat /dev/null > filename`
## 文件目录
### 创建文件目录
* `mkdir dirName`
### 切换指定目录
`cd 目录名称`
* `ll` 列出结果详细，有时间，是否可读写等信息
* `ls` 列出文件名或目录名
### 删除指定目录
`rm 目录名称 -r`
### 删除指定目录及其所属文件
`rm -rf 目录路径名称`
### 删除指定目录下所有文件（不删除文件夹）
`rm -rf 目录路径名称/*`
### 退出当前目录
* `cd ..` 上层目录
* `cd `是home目录
* `cd /` 根目录

# 虚拟机
## 退出xshell，如何保持程序依然运行
`nohup 命令 &`
例如 `nohup npm run dev &`,随后服务正常启动，显示`[~]$ appending output to nohup.out` ,不能直接关闭xshell，退出程序正确方法：按任意键，输入`exit`，随后关闭xshell，服务会在后台一直启动中<br/>  
参考文档：https://www.cnblogs.com/wangyanhua95/p/7954019.html

## 杀进程
``` javascript
\\查进程
ps -ef | grep npm   \\查找npm的进程

//会返回类似 501 27562 25664   0  8:35pm ttys001    0:00.00 grep npm
\\ 然后执行命令:
kill 501
```

