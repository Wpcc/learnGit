# LEARN GIT
___

## 第一部分 git新建文件

#### 初始化版本控制工具git  
--命令行：$ git init
#### 查看文件目录
--命令行：$ pwd  //非必要
#### 创建文件  
--命令行：$ touch filename  
#### 添加文件  
--命令行：$ git add filename  
#### 提交文件并留言  
--命令行：$ git commit -m "content"

命令语句缩写解释：  
pwd：print work directory  
m: message  

## 第二部分 git修改文件

git储存：本地git版本控制工具的储存分两个区域，工作区和版本库。  
版本库又分为：暂存区（stage）以及主存区（master）  
![resp](./img/git-stage.jpg)
#### 修改文件而并未提交可以查看储存状态
命令行：$ git status
#### 需要查看修改文件的详细信息：  
命令行：$ git diff filename  

#### 命令语句缩写解释：
diff:different

## 第三部分 git回溯机制

### 回溯  

在git工具中HEAD代表当前版本，上一个版本是HEAD^，以此类推。  
回溯太远的话可以简写HEAD~12。
git中每一次对master的提交都有一个唯一的ID  
#### 我们可以回溯到当前版本
命令行语句：$ git reset --hard HEAD  
#### 当然也可以回溯版本号：  
命令行：$ git reset --hard commit_ID  
#### 也可以通过打印修改记录查看到版本号  
命令行：$ git log  
#### 有时候回溯会导致当前版本消失  
可以查看操作历史： $ git reflog
查看暂存区的命令：$ cat filename

### 删除

#### 删除工作区文件--直接调用命令行语句  
命令行：$ rm filename  
#### 查看储存状态--工作区和版本库文件不一致
命令行：$ git status  
1. 删除版本库文件
删除命令行：$ git rm filename
提交命令行：$ git commit -m 'content'
2. 恢复版本库文件  
恢复命令行： $ git checkout -- filename

## 第四部分 git远程仓库

git的定义是分布式版本控制系统，也就是说除了我们本身电脑上的仓库外，  
一定还存在着一个服务器仓库，控制交互着每一个共同开发者的仓库。  
以github网站为例。

#### 创建远程仓库  

git和github之间的传输是通过SSH加密的，首先需要设置的就是SSH key。
