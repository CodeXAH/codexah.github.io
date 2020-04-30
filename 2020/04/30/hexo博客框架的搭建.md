# hexo博客框架的搭建

### 1.安装Node.js

1）因为Hexo框架是通过Node.js生成，所以首先根据自己的操作系统安装相应的版本，下载链接：<http://node.js.org/>

2）下载完成后一直Next就可以了

3）使用Win+R在cmd命令行中输入node -v查看node版本，若出现版本信息则安装成功。

### 2.搭建Hexo框架

安装Hexo框架需要使用npm包管理器。

安装命令为：npm install -g hexo-cli来安装hexo

*由于npm代码仓库的服务器在国外，由于Great Firewall的缘故，下载速度可能不尽如人意，这时你可以使用淘宝的npm代码仓库，通过npm安装cnpm：**npm install -g cnpm --registry=https://registry.npm.taobao.org**安装成功后，可以通过以下命令查看cnpm版本：**cnpm -v**通过cnpm来操作下载速度会得到很大提升，但包的版本不一定是最新的*作者：淡写回忆链接：https://www.jianshu.com/p/3ca4f0d01dee来源：简书著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。

### 3.建立本地博客目录

1）在命令行中进行以下操作：可以选择自己要存放的路径

- 新建目录book：mkdir book
- 进入book目录下 ：cd book
- 新建blog目录：mkdir blog
- 进入到blog目录下：cd blog

2）初始化博客：hexo init

出现此代码就说明成功初始化

![](images/QQ图片20200430091629.png)

### 4.启动hexo博客

1）直接在命令行中输入：hexo s即可启动，启动后在浏览器中访问localhost:4000

![](images/QQ图片20200430092154.png)

2）进入后可以看到各种hexo博客的操作

- 在博客中创建新文章：hexo new "my post"
- 部署：hexo beploy
- 启动服务：hexo s
- 生成静态文件：hexo generate

### 5.新建自己的文章

1）在命令行中输入：hexo new "my post"编写文章内容

2）也可以在D:\book\blog\source\\_posts添加文章一样会在博客中显示

### 6.切换主题

1）可以在github上面选择自己喜欢的主题，例如我选择的主题为：<https://github.com/jerryc127/hexo-theme-butterfly>

2）在blog目录下下载butterfly主题:

![](images/QQ图片20200430094305.png)

详述：就是使用git命令来下载主题到themes/butterfly目录下，但是首先需要在浏览器中下载git。

3）将主题配置到博客上面去：

需要打开blog/_config.yml文件，找到theme并更改为自己的主题

![](images/QQ图片20200430094859.png)

4）然后在命令行中输入：hexo clean清理一下

5）输入：hexo g重新生成内容

6）输入：hexo s在次启动服务器查看博客内容

7）要是切换的主题不能正常显示，打开butterfly/layout文件夹，发现文件全是.pug结尾，我们可以知道该主题使用的模板引擎是pug模板引擎，且在butterfly/source/css的文件中是以.styl结尾，所以该主题还需要安装Stylus，对于其他结尾的文件可能需要安装其他解析器。

8）主题需要pug和stylus的渲染，可以在命令行中键入：

npm install --save hexo-renderer-jade hexo-generator-feed hexo-generator-sitemap hexo-browsersync hexo-generator-archive

9）然后在命令行中输入：hexo clean清理一下

10）输入：hexo g重新生成内容

11）最后在输入：hexo s就可以成功的切换主题了

### 7.部署

1）登陆自己的github，new一个新的仓库

![](images/16603653-10de997b586e0b04.webp)

然后直接create新建即可

![](images/16603653-f9fc001519ca4f76.webp)

1、回到命令行下blog目录安装一个部署到github的插件：

npm install --save hexo-deployer-git

2、打开这个路径

![](images/16603653-20f5a2e80862dd83.webp)

修改此处为：

![](images/16603653-4c83447a7df8f111.webp)

repo处填写创建仓库的地址：

![](images/16603653-cce2a9ee029a1f54.webp)

最后直接部署到远端就可以了：hexo d（可能会要求输入github密码）

参考链接：<https://www.jianshu.com/p/3ca4f0d01dee>







