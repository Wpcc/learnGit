### learn git
===

#### 第一部分 git新建文件

初始化版本控制工具git：$ git init  
查看文件目录： $ pwd  --非必要
创建文件：$ touch filename  
添加文件：$ git add filename  
提交文件并留言： $ git commit -m "content"

命令语句缩写解释：
pwd：print work directory  
m: message  

#### 第二部分 git修改文件

如果修改文件而并未提交：$ git status  
--查看当前文件状态  
需要查看修改而为提交的详细信息： $ git diff filename  

命令语句缩写解释：
diff:different

#### 第三部分 git回溯机制

HEAD代表当前版本，上一个版本是HEAD^，以此类推。  
回溯太远的话可以是HEAD~12  
命令行语句：$ git reset --hard HEAD  
当然也可以回溯版本号：$ git reset --hard commit_ID  
打印修改记录可以查看到版本号：$ git log  
--有时候回溯会导致当前部位消失  
可以查看操作历史： $ git reflog
查看暂存区的命令：$ cat filename
