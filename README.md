# caozha-tp-comment（功能强大的评论系统）

caozha-tp-comment，一个功能强大的评论系统，基于开源的ThinkPHP开发，特点：易上手，零门槛，界面清爽极简，极便于二次开发。

可以自动适配电脑、平板和手机等不同客户端。

### 演示地址

[http://caozha.com/git/demo/caozha-admin/public/index/comment/index](http://caozha.com/git/demo/caozha-admin/public/index/comment/index)


### 其他版本

1、此为thinkphp版本的评论系统，如需要原生PHP写的评论系统，请移步：[caozha-comment](http://gitee.com/caozha/caozha-comment)。

2、此源码不含后台，如需要后台，请参考：[caozha-admin](http://gitee.com/caozha/caozha-admin)，内有评论的完整后台示例。


### 安装使用

**快速安装**

1、PHP版本必须7.1及以上。

2、上传目录/Src/内所有源码到服务器，并设置网站的根目录指向运行目录/public/。（此为ThinkPHP6.0的要求）

3、将/Database/目录里的.sql文件导入到MYSQL数据库。

4、修改文件/config/database.php，配置您的数据库信息（如果测试时启用了/.env，还需要修改文件/.env，系统会优先使用此配置文件）。

5、后台访问地址：http://您的域名/admin/index/login   (账号：caozha   密码：123456)


**伪静态设置**

1、ThinkPHP框架必须在根目录下设置伪静态才能正常访问，否则会显示404错误。

2、如果您使用的是Apache，伪静态设置为（.htaccess）：

<IfModule mod_rewrite.c>

  Options +FollowSymlinks -Multiviews
  
  RewriteEngine On
  
  RewriteCond %{REQUEST_FILENAME} !-d
  
  RewriteCond %{REQUEST_FILENAME} !-f
  
  RewriteRule ^(.*)$ index.php?s=$1 [QSA,PT,L]
  
</IfModule>


3、如果您使用的是Nginx，伪静态设置为：

location / {

    index index.php;
    
    if (!-e $request_filename) {
    
       rewrite  ^(.*)$  /index.php?s=/$1  last;
       
       break;
       
    }
    
}


4、在网站根目录（/public/）下，有两个文件：.htaccess和nginx.htaccess，分别是Apache和Nginx的伪静态文件，您可以直接拿来使用。


**评论参数设置：**

**修改模板：** 

打开\app\index\view\comment\index.html，可以为每篇文章或者需要评论的模块添加唯一ID：

<div class="pl-520am" data-cmtid="act_1" data-catid="0" ></div>

上面的data-cmtid是评论标识符ID，data-catid是评论标识符分类ID，这两个参数是用来区分文章等评论的，一般情况下使用data-cmtid就足够了。

**修改控制器：** 

打开\app\index\controller\comment.php，找到$cmt_config，可以设置评论每页的数量、验证码、缓存、是否需要审核、是否允许发图片、滚动自动加载、屏蔽词等等。

**修改评论表情：** 

打开\app\common.php，修改函数comment_face()，把不需要的表情注释掉就好了，当然也可以添加更多自定义表情。


### 特别鸣谢

caozha-tp-comment使用了以下开源代码：

ThinkPHP6.0.2、lgyPl

特别致谢！

### 赞助支持：

支持本程序，请到Gitee和GitHub给我们点Star！

Gitee：https://gitee.com/caozha/caozha-tp-comment

GitHub：https://github.com/cao-zha/caozha-tp-comment

### 关于开发者

开发：草札 www.caozha.com

鸣谢：品络 www.pinluo.com  &ensp;  穷店 www.qiongdian.com


### 界面预览


**评论界面（PC）：**

![输入图片说明](https://images.gitee.com/uploads/images/2020/0611/145140_3e613b5d_7397417.png "16.png")

![输入图片说明](https://images.gitee.com/uploads/images/2020/0611/135914_73eb0310_7397417.png "19.png")

  
  

**评论界面（手机）：**

![输入图片说明](https://images.gitee.com/uploads/images/2020/0612/152711_77208177_7397417.jpeg "5.jpg")

 
![输入图片说明](https://images.gitee.com/uploads/images/2020/0612/152720_633821db_7397417.jpeg "6.jpg")
 

**评论可设置项**

![输入图片说明](https://images.gitee.com/uploads/images/2020/0612/182435_49bc1745_7397417.png "1.png")

 
 
![输入图片说明](https://images.gitee.com/uploads/images/2020/0612/152743_d68c30f1_7397417.png "2.png")
