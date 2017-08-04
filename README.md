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
### 删除指定目录下所有文件（不删除文件夹）
`rm -rf 目录路径名称/*`
### 退出当前目录
* `cd ..` 上层目录
* `cd `是home目录
* `cd /` 根目录
