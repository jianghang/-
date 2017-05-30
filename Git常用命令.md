####Git常用命令
* 连接远程仓库--git remote add origin https://github.com/jianghang/notes.git
* fatal: refusing to merge unrelated histories本地仓库连接远程仓库报的错误，原因为是两个为不同的项目，解决方法：git pull origin master --allow-unrelated-histories