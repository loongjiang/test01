# GIT工作原理
* 工作区
* 暂存区
* 历史区
* 中央仓库
> 工作区 -> 暂存区
* git add -A
> 暂存区 -> 历史区
* git commit -m"some comments"
> 历史区 -> 中央仓库
* git pull origin master
> 历史区 <- 中央仓库
* git push origin master

# GIT的全局配置
> 第一次安装完成git后，我们在全局环境配置基本信息，告诉git我是谁？
```bash
git config --list          #查看配置信息
git config --global --list #查看全局配置信息

git config --global user.name 'xxxx'        #配置全局用户名
git config --global user.email 'xxxx@xx.xx' #配置全局用户邮箱
```
# 创建仓库，完成版本控制
## 创建本地仓库
```bash
git init   # 初始化一个本地仓库
```
> PS: 注意：git init 会在当前目录生成一个".git"的隐藏文件夹，千万别删除这个文件夹，暂存区和历史区还有本仓库的其他配置信息就是存在里面，这是git工作的空间，如果该空间遭到破坏，git将不能正常地进行版本管理

```bash
Initialized empty Git repository in D:/dev/mygit/test01/.git/
```
> PS: 如果shell返回上述信息，则表明本地仓库初始化成功

## 将文件从工作区添加到暂存区：
```bash
git add xxx     #把某个文件或文件夹添加到暂存区
git add . 或 -A #把当前仓库中所有最新修改的文件都添加到暂存区
```
```bash
git status      #查看当前文件(夹)的状态
```
> PS:<br/>
> 红色: 代表文件在工作区<br/>
> 绿色: 代表文件在暂存区<br/>
> 空的: 表示所有修改都已经提交到历史区

## 将暂存区文件提交到历史区
```bash
git commit -m'本次提交内容描述'
```
> PS: 选项 -m 后面没有空格！！！

# 查看操作日志
```bash
git log
```

# git和github
> github https://gighub.com<br/>
这是一个网站（一个开源的源代码管理平台），用户注册后，可以在自己的账户下创建仓库，用来管理项目的源代码（源代码基于git传到平台中）<br/>
```bash
git remote -v   #查看本地仓库和哪个远程仓库在保持连接
git remote add origin [本地仓库]
```

