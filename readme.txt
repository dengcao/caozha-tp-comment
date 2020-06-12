caozha-tp-comment（功能强大的评论系统）

【简介】

caozha-tp-comment，一个功能强大的评论系统，基于开源的ThinkPHP开发，特点：易上手，零门槛，界面清爽极简，极便于二次开发。
可以自动适配电脑、平板和手机等不同客户端。
（注意：此源码不含后台，如需要后台，请参考：caozha-admin（https://gitee.com/caozha/caozha-admin），内有评论的完整后台示例。）

【演示地址】

http://caozha.com/git/demo/caozha-admin/public/index/comment/index


【安装使用】

快速安装：

1、PHP版本必须7.1及以上。

2、上传目录/Src/内所有源码到服务器，并设置网站的根目录指向目录/Src/public/。（TP6.0要求）

3、将/Database/目录里的.sql文件导入到MYSQL数据库。

4、修改文件/Src/config/database.php，配置您的数据库信息（如果是本地测试，还需要修改文件/Src/.env，本地测试会优先使用此配置文件）。

5、评论访问地址：http://您的域名/index/comment/index

评论参数设置：

修改模板：

打开\Src\app\index\view\comment\index.html，可以为每篇文章或者需要评论的模块添加唯一ID：

上面的data-cmtid是评论标识符ID，data-catid是评论标识符分类ID，这两个参数是用来区分文章等评论的，一般情况下使用data-cmtid就足够了。

修改控制器：

打开\Src\app\index\controller\comment.php，找到$cmt_config，可以设置评论每页的数量、验证码、缓存、是否需要审核、是否允许发图片、滚动自动加载、屏蔽词等等。

修改评论表情：

打开\Src\app\common.php，修改函数comment_face()，把不需要的表情注释掉就好了，当然也可以添加更多自定义表情。

【特别鸣谢】

caozha-tp-comment使用了以下开源代码：

ThinkPHP6.0.2、lgyPl

特别致谢！

【赞助支持】

支持本程序，请到Gitee和GitHub给我们点Star！

Gitee：https://gitee.com/caozha/caozha-tp-comment

GitHub：https://github.com/cao-zha/caozha-tp-comment

【关于开发者】

开发：草札 www.caozha.com

鸣谢：品络 www.pinluo.com   穷店 www.qiongdian.com

