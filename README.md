# git_operation

github  将fork的项目和原来的项目保持一致

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
