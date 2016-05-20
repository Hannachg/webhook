#github gitblog 自动化部署方案

>webhook 

    github提供webhook就是你每次提交会向你指定的url发一个post请求,我们监听这个请求就可以实现自动更新博客文件.


>大概流程

    git push > github post > node hanlde event > git pull

>准备

    安装node环境(自行安装)
    安装node进程管理工具
    npm install pm2 -g
    
    

>使用
    
    github:
    
    github新建项目 
    点击项目上的setting > Webhooks & service
    设置payload url 为你服务器监听的那个路径

    vps:
    
    将webhook项目和你的gitblog项目放到同一个目录下
    修改 update.sh  WEB_PATH='/www/gitblog文件夹名'

    修改index.js secret 要修改你在github上面设置的secret
    我的是crack

    进入webhook文件夹 
    pm2 start index.js
    
    在你本地修改下博客文件 git push 看有没有成功触发。
>如果有用麻烦给个star

参考链接:http://www.lovelucy.info/auto-deploy-website-by-webhooks-of-github-and-gitlab.html







