# git团队协作

## 基本命令

### 设置签名

设置用户名和邮箱，`--global`标签表示全局生效，否则只在当前项目生效（如果不设置，提交代码会报错）

```
git config --global user.name 用户名
git config --global user.email 邮箱
```

### 本地仓库管理

#### 初始化本地库

```
git init
```

#### 查看本地库状态

会显示变更的部分

```
git status
```

#### 添加到暂存区

```
// 添加指定文件
git add 文件名

// 添加所有文件
git add .
```

#### 提交到本地库

```
// 添加指定文件
git commit -m "日志信息" 文件名

// 添加所有文件
git commit -m "日志信息" .
```

#### 查看历史记录

```
git reflog
```



## 版本穿梭

#### 1.查看历史记录

```
git reflog

// 指定文件的修改记录
git blame <file>
```

显示每次提交的历史记录

#### 2.跳到指定版本

```
// 基于索引值(版本号)操作
git reset --hard [局部索引值]
git reset --hard a6ace91
```

参数说明

- --soft ：仅仅在本地库移动HEAD 指针
- --mixed ：在本地库移动HEAD 指针；重置暂存区
- --hard 参数：在本地库移动HEAD 指针；重置暂存区；重置工作区



## 远程仓库管理

### 仓库克隆

本地目录可忽略，自动生成

```
git clone <仓库路径>[本地目录]
```

### 设置和查看别名

远程仓库一般是很长的网址，不方便输入，可以通过设置别名代替仓库地址

```
// 设置别名
git remote add [别名] [远程地址]
git remote add dy https://github.com/Toyken-P/Tiktok-demo.git

// 查看所有设置的别名
git remote -v
```

### 远程仓库抓取

抓取指将仓库里的更新都抓取到本地，但不会进行合并

```
git fetch [remote name] [branch name]
```

### 远程仓库拉取

抓取指从远程获取代码并合并本地的版本

```
git pull <远程主机名> <远程分支名>:<本地分支名>
```

### 远程仓库推送

抓取指将仓库里的更新都抓取到本地，但不会进行合并

```
git push <远程主机名> <本地分支名>:<远程分支名>
```



