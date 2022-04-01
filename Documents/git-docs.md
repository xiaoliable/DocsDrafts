
2022年04月01日21:20:21
记日志工作Excel时，发现本地的md文档不像有道云笔记可以查修改时间。想到可以把本地文件git管理起来，不是更有仪式感，更能有效追踪、便于review吗！！！？
天才！。估计别人十年前就想到了。

然后sb似的，开了个新坑，挖了个老坑——git！。
https://cloud.tencent.com/developer/article/1504684
Git的使用--如何将本地项目上传到Github（三种简单、方便的方法）（二）（详解）
2019-09-11阅读 61.7K0

其中ssh等等一直没看懂。

1、git init      （建立本地仓库）
2、git add  *  (将代码添加到本地仓库，《*是添加全部代码，代码全部更新》)
3、git commit -m "first commit"  (提交到本地缓冲，《引号里说明提交了什么东西，说白了就是注释》）
4、git remote add origin https://github.com/hongduhong/test.git   （将本地仓库的代码提交远程github的仓库，《后面的地址就是之前创建github的远程仓库地址》）
5、git push -u origin master    （将远程仓库的代码 push到master分支上）



 这是由于你新创建的那个仓库里面的README文件不在本地仓库目录中，这时我们可以通过以下命令先将内容合并以下：

$ git pull --rebase origin master
       这时你再push就能成功了。

     总结：其实只需要进行下面几步就能把本地项目上传到Github
     1、在本地创建一个版本库（即文件夹），通过git init把它变成Git仓库；
     2、把项目复制到这个文件夹里面，再通过git add .把项目添加到仓库；
     3、再通过git commit -m "注释内容"把项目提交到仓库；
     4、在Github上设置好SSH密钥后，新建一个远程仓库，通过git remote add origin https://github.com/guyibang/TEST2.git将本地仓库和远程仓库进行关联；
     5、最后通过git push -u origin master把本地仓库的项目推送到远程仓库（也就是Github）上；（若新建远程仓库的时候自动创建了README文件会报错，解决办法看上面）。
