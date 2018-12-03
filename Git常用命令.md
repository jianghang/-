#### Git常用命令
* 连接远程仓库--git remote add origin https://github.com/jianghang/notes.git
* fatal: refusing to merge unrelated histories本地仓库连接远程仓库报的错误，原因为是两个为不同的项目，解决方法：git pull origin master --allow-unrelated-histories
* git update-index --assume-unchanged your_file_path不想继续追踪某个文件
* git update-index --no-assume-unchanged your_file_path再次继续跟踪某个文件 
* git config credential.helper 'cache --timeout=3600' 记住用户名密码，时间为一个小时
* git config --global credential.helper store 长期存储密码
* git config --global http.proxy 配合下一条命令解决push不了的问题
* git config --global --unset http.proxy 
* git config user.name 'xxxx' 在项目内运行设置本项目的用户名
* git config user.email 'xxxx@qq.com' 在项目内设置本项目的邮箱