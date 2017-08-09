### learn git
___

#### 第一部分 git新建文件
___
初始化版本控制工具git：$ git init  
查看文件目录： $ pwd  --非必要
创建文件：$ touch filename  
添加文件：$ git add filename  
提交文件并留言： $ git commit -m "content"

命令语句缩写解释：
pwd：print work directory  
m: message  

#### 第二部分 git修改文件
___
如果修改文件而并未提交：$ git status  
--查看当前文件状态  
需要查看修改而为提交的详细信息： $ git diff filename  

命令语句缩写解释：
diff:different