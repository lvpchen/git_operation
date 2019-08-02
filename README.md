# git_operation

git使用五部曲
1. 先拉取代码
    git pull
2. 修改内容,并查看修改文件
    git status
3. 增加修改
    git add "文件名"
4. 提交修改
    git commit -m "修改说明"
5. 提交到远程分支
    git push

github:将fork的项目和原来的项目保持一致

1. 将github上fork别人的项目clone到本地

        git clone https://github.com/my_fork/project.git

2. 切换到project 目录下，然后增加远程分支(fork的分支)，名为 update_stream（名字任意）到本地

        git remote add update_stream https://github.com/original/project.git

3. 运行命令：`git remote -v`, 会发现多出来了一个update_stream的远程分支

        git remote -v

4. 然后把远程原始分支 update_stream 的代码拉到本地  

        git fetch update_stream
 
5. 合并对方远程原始分支 update_stream 的代码

        git merge update_stream/master

6. 最后把最新的代码推送到你的github上

    git push origin master

7. 如果需要给update_stream发送Pull Request

    打开 `https://github.com/my_fork/project.git`  
    点击Pull Request -> 点击New Pull Request -> 输入Title和功能说明 -> 点击Send pull request

如果第6步出现问题：   
fatal: remote error: 
  You can't push to git://github.com/lvpchen/project.git
  Use https://github.com/lvpchen/project.git

原因：
clone的时候选择http协议导致的。用https://github.com/username/project.git。只有读的权限，不能写入，导致不能push。

解决方法：
删除远程分支：git remote rm update_stream
要用ssh协议才能push，所以clone用git@github.com:username/project.git

增加远程分支：git remote add update_stream git@github.com:orignal_username/project.git
