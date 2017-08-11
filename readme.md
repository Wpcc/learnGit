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

### 创建远程仓库  

git和github之间的传输是通过SSH加密的，首先需要设置的就是SSH key。  
#### 在本地创建ssh key  
命令行： $ ssh-keygen -t rsa -C 'youremail@example.com'  
执行命令行会在本地（用户目录下）创建两个密钥，一个公钥id_rsa.pub，一个私钥id_rsa，在和github远程仓库进行绑定的时候会用到公钥。  
![ssh](.img/ssh.png)  
#### 创建远程仓库  
当我们在github上进行公钥连接，也就意味着本地取得远程仓库的使用权，接下来我们需要在github上创建远程仓库。  
![create-repo1](.img/create-repo1.png)  
![create-rep02](./img/create-rep2.png)  
创建完成后可以获取到远程仓库的地址，并让本地仓库与之关联。  
命令行： $ git remote add origin git@github.con:Wpcc.learnGit.git  
远程仓库需要换成与之关联的仓库。
由于第一次创建的远程仓库内容为空，我们需要进行第一次推送。  
命令行： $ git push -u origin master  

#### 克隆远程仓库  
命令行1：$ git clone git@github.com:Wpcc/learnGit.git  
命令行2：$ git clone https://github.com/Wpcc/learnGit.git 

#### 命令行解释  
-u 推送内容并让本地仓库与远程仓库关联 一般出现在第一次推送当中  

## 本地分支  

### 创建合并分支  

#### 查看分支  
命令行： $ git branch  
#### 创建分支  
命令行： $ git branch <name>  
#### 切换分支  
命令行：$ git checkout <name>  
#### 创建+切换分支：  
命令行：$ git checkout -b <name>  
#### 合并某分支到当前分支：  
命令行：$ git merge <name>
#### 删除分支  
命令行： $ git branch -d <name>

### 分支冲突  
1. 当本地两个分支有各自的修改，合并的时候会产生冲突，因为系统不知道哪种分支的修改需要保留，哪种分支的修改需要删除，这个时候我们需要手动修改。  
2. 