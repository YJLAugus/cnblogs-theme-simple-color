## 写在前面

> 本款主题是基于 [@esofar](https://www.cnblogs.com/esofar/)大佬的`silence`主题，稍加更改完成。喜欢主题的极简风，同时也适配了许多个性化的东西，所以，主题总体基本没有任何的优化，代码凌乱，本不想放出，毕竟代码混乱，毫无逻辑可言，近期有许多小伙伴想要这一套主题，特此放出。不当之处定会有许多，请多担待。同时也部分参考了[GShang](https://www.cnblogs.com/gshang)学长的博客，特表感谢。

### 功能简介

* 移动端适配
* 极简白，夜间黑，清新透明，玻璃磨砂 四种主题模式自动切换
* 音乐播放器
* 图片灯箱
* 文章自动目录生成

## 主题预览

夜间黑主题：<input type="button" value="开启/关闭夜间模式" onclick="switchNightMode();">。超级美丽漂亮可爱的小姐姐主题：<input type="button" value="开启/关闭MM模式" onclick="switchModelMode();">。阔耐的动漫主题：<input type="button" value="开启/关闭ercy模式" onclick="switchModelErcyMode();">，或者点击博客左上角<i class="fa fa-cog fa-spin fa-lg "></i>进行预览。
### 极简白

个人比较喜欢的一个样式，极简风。

<img src="https://img.imjad.cn/images/2019/09/16/cf60caef8fc2573c.png" data-action="zoom">

### 夜间黑

不能算是博客的一种主题，你可以理解为`夜间模式`。

<img src="https://img.imjad.cn/images/2019/09/16/3ee172534d347e92.png" data-action="zoom">

### 清新透明 

喜欢极致色彩的朋友。

<img src="https://img.imjad.cn/images/2019/09/16/ab69b496fc02f38c.png" data-action="zoom">

### 玻璃磨砂

毛玻璃磨砂质感。

<img src="https://img.imjad.cn/images/2019/09/16/201e4aa12cf5556e.png" data-action="zoom">

## 主题部署

### 一键部署
<p>
    <div class="info"><p>如果你想快速搭建出和本博客一样的主题样式，请查看下面这句说明。当然，前提是你得有<font  color="red">js权限。</font></p></div>
</p>

如果想部署和当前博客一样的样式。直接下载整个主题，[下载地址](#MySignature) 见文章末尾。把**页脚**，**页首**，**侧边栏**的代码粘贴到你的博客后台，然后**更改一下其中的文件链接地址**即可。下面的部署文档只为了个性化定制而写，如果你想个性化的定制博客主题，请接着往下看，

### 基本部署

* 前提：已经开通`js`权限，没开通的可以向博客园官方申请开通。

* 引入文件

  可以放在`页脚`。

  ```html
  <script src="https://example.com/simple-color.js"></script>
  ```

* 引入样式

  把**simple-color.css**中的代码粘贴在`自定义css样式中`。

* 选择模板

  具体的设置如下图。

<img src="https://img.imjad.cn/images/2019/09/16/Snipaste_2019-09-16_16-29-00.png"  data-action="zoom">

* 头部菜单设置

  把下面链接中的地址换成你自己的`文章`或者`随笔`的地址就好。下面函数在`simple-color.js`文件中。

  ```javascript
  function() {
                  var e = this,
                  t = p(this.cnblogs.blogTitle).find("h1 a").html(),
                  a = p(this.cnblogs.publicProfile).find("a:eq(0)").html(),
                  o = p("head").find("title");
                  //o.html(o.html().replace(a + " - 博客园", "" + t));
                  var n = p(this.cnblogs.navList);
  				n.find("li").eq(1).after('<li><a id="blog_nav_tags" class="menu" href="https://www.cnblogs.com/' + currentBlogApp + '/tag">标签</a></li>'),
  				n.find("li").eq(2).after('<li><a id="blog_nav_tags" class="menu" href="https://www.cnblogs.com/yjlaugus/p/7705340.html ">关于</a></li>'),
  				n.find("li").eq(3).after('<li><a id="blog_nav_tags" class="menu" href="https://www.cnblogs.com/yjlaugus/articles/weibo.html">微语</a></li>'),
  				n.find("li").eq(4).after('<li><a id="blog_nav_tags" class="menu" href="https://www.cnblogs.com/yjlaugus/p/7857317.html ">投喂</a></li>'),
  				n.find("li").eq(5).after('<li><a id="blog_nav_tags" class="menu" href="https://www.cnblogs.com/yjlaugus/p/8724650.html">友链</a></li>'),
                  p.each(n.find("li"),
                  function(e, t) {
                      p(t).append("<i></i>")
                  }),
                  p("body").prepend('<div class="esa-mobile-menu"></div>'),
                  p(".esa-mobile-menu").on("click",
                  function() {
                      p(e.cnblogs.navigator).fadeToggle(200)
                  })
              }
  ```

  

这样一个主题基本完成，如果想加其余的功能，接着往下看。

* 脚本设置

  为了提高园友的阅读体验，主题在博客园原有功能基础上追加了一些辅助阅读、以及人性化的功能模块。其中部分模块做了参数配置，用户可根据自己意愿选择是否启用。若启用，再根据自己的信息或写作习惯设置相关参数。

  进入『[设置](https://i.cnblogs.com/Configure.aspx)』界面，将如下脚本代码引用 **追加** 到`「博客侧边栏公告」`文本域中，其中配置参数根据下表自行修改。这个配置是来自[silence部署文档](https://github.com/esofar/cnblogs-theme-silence/blob/master/docs/deploy.mdr)。

  ```javas
  <!-- 放在侧边栏-->
  <script type="text/javascript">
      $.silence({
          profile: {
              enable: true,
              avatar: '',
              favicon: 'https://files-cdn.cnblogs.com/files/yjlaugus/favicon.ico',
          },
          catalog: {
              enable: true,
              move: true,
              index: true,
              level1: 'h2',
              level2: 'h3',
              level3: 'h4',
          },
          signature: {
              enable: true,
              home: 'https://yjlaugus.cnblogs.com/',
              license: 'CC BY 4.0',
              link: 'https://creativecommons.org/licenses/by/4.0'
          },
         reward: {
              enable: true,
              title: '『一键投喂 软糖/蛋糕/布丁/牛奶/冰阔乐！』',
              wechat: 'https://www.cnblogs.com/images/cnblogs_com/yjlblog/1280680/o_wx_zfx.png',
              alipay: 'https://www.cnblogs.com/images/cnblogs_com/yjlblog/1280680/o_zfb_zfx.png',
          },     
          github: {
              enable: false,
              color: '#fff',
              fill: null,
              link: 'https://github.com/YJLAugus/'
          }
      });
  </script>
  
  
  ```

  ```
  <!--随笔发布信息 放在侧边栏-->
  <script>
  if ($("#topics")!=null){
  $("#cnblogs_post_body").before("<p class='publishinfo'><img src='https://img.shields.io/badge/Post-"+$("#post-date").text().replace(/\-/g,"--").replace(/\ /g,"%20").replace(/\:/g,"%3A")+"-blue'/>"+
  
  "<img src='https://img.shields.io/badge/Read-" + $("#post_view_count").text() + "-red'/>" +
  
  "<img src='https://img.shields.io/badge/Comment-" + $("#post_comment_count").text() + "-green'/><br/>" +
   $("#BlogPostCategory").html() + $("#EntryTag").html() +"</p>")
  }
  </script>
  
  <!--首页排版调整 放在侧边栏-->
  <script>
  for(i=0;i<=$(".desc_img").length;i++){
  $(".desc_img").eq(i).insertBefore($(".postTitle").eq(i));
  $(".postDesc").eq(i).insertAfter($(".day .postTitle").eq(i));
  }
  for(i=0;i<=$(".entrylistPostSummary").length;i++){
  $(".desc_img").eq(i).insertBefore($(".entrylistPosttitle").eq(i));
  $(".entrylistItemPostDesc").eq(i).insertAfter($(".entrylistPosttitle").eq(i));
  }
  </script>
  ```

  

  配置参数说明表：

  | 模块                     | 属性             | 说明     | 类型                                                | 默认值 |
  | ------------------------ | ---------------- | -------- | --------------------------------------------------- | ------ |
  | base（基础信息）         | avatar           | 博主头像 | String                                              | null   |
  | favicon                  | 网页标题图标     | String   | null                                                |        |
  | catalog（博文目录）      | enable           | 是否启用 | Boolean                                             | false  |
  | move                     | 是否允许拖拽     | Boolean  | true                                                |        |
  | index                    | 是否显示索引     | Boolean  | true                                                |        |
  | level1                   | 一级标题         | String   | h2                                                  |        |
  | level2                   | 二级标题         | String   | h3                                                  |        |
  | level3                   | 三级标题         | String   | h4                                                  |        |
  | signature（博文签名）    | enable           | 是否启用 | Boolean                                             | false  |
  | auther                   | 作者名字         | String   | [Blog Nickname]                                     |        |
  | home                     | 作者主页         | String   | [https://www.cnblogs.com](https://www.cnblogs.com/) |        |
  | license                  | 许可证名称       | String   | CC BY 4.0                                           |        |
  | link                     | 许可证链接       | String   | https://creativecommons.org/licenses/by/4.0         |        |
  | sponsor（博文赞赏）      | enable           | 是否启用 | Boolean                                             | false  |
  | text                     | 标题             | String   | Sponsor                                             |        |
  | paypal                   | PayPal 收款地址  | String   | null                                                |        |
  | alipay                   | 支付宝收款二维码 | String   | null                                                |        |
  | wechat                   | 微信收款二维码   | String   | null                                                |        |
  | github（GitHub Corners） | enable           | 是否启用 | Boolean                                             | false  |
  | fill                     | 背景填充色       | String   | [Silence Theme Color]                               |        |
  | color                    | 章鱼猫颜色       | String   | #fff                                                |        |
  | link                     | Github 链接      | String   | null                                                |        |

  配置完成后，记得点击「保存」按钮，保存上述操作。

* 补充说明

  进入『[设置](https://i.cnblogs.com/Configure.aspx)』界面，在「标题」文本框中设置博客标题，注意不支持显示「子标题」；在「博客皮肤」处选择博客园官方标准模板 **Custom**；把「禁用模板默认CSS」复选框取消勾选。最后，点击「保存」按钮保存上述 3 步操作。

  进入『[选项](https://i.cnblogs.com/Preferences.aspx)』界面，在「控件显示设置」中需要勾选的博客园官方功能模块如下几个：

  - 必须要勾选：公告、我的标签、随笔分类、阅读排行榜、推荐排行榜
  - 自定义勾选：博客园链接、首页链接、RSS订阅、联系

  其他模块取消勾选(可选操作)。最后，点击「SAVE」按钮保存操作。

### 个性定制

#### 博客自动更换主题

实现四种主题样式自定义切换。点击博客左上角的<i class="fa fa-cog fa-spin fa-lg "></i> 试试看！当然，如果你还不满足于现在的主题样式，可以自己定制自己的主题样式，详细请转看文章[还在美化博客吗？试试一键更换博客主题吧！](https://www.cnblogs.com/yjlaugus/p/11223861.html)

```
<!--主题切换 放在侧边栏-->
<script>
	$('.fa.fa-cog.fa-spin.fa-lg').click(function () {
	    $(this).closest('.float-btn-group').toggleClass('open');
	});
</script>
```

```
<!--主题切换放在侧边栏-->
<script>

function switchNightMode(){
    var night = document.cookie.replace(/(?:(?:^|.*;\s*)night\s*\=\s*([^;]*).*$)|^.*$/, "$1") || '0';
    if(night == '0'){
        document.body.classList.add('night');
        document.cookie = "night=1;path=/"
        console.log('夜间模式开启');
    }else{
        document.body.classList.remove('night');
        document.cookie = "night=0;path=/"
        console.log('夜间模式关闭');
    }
}

(function(){
    if(document.cookie.replace(/(?:(?:^|.*;\s*)night\s*\=\s*([^;]*).*$)|^.*$/, "$1") === ''){
        if(new Date().getHours() > 22 || new Date().getHours() < 6){
            document.body.classList.add('night');
            document.cookie = "night=1;path=/";
            console.log('夜间模式开启');
        }else{
            document.body.classList.remove('night');
            document.cookie = "night=0;path=/";
            console.log('夜间模式关闭');
        }
    }else{
        var night = document.cookie.replace(/(?:(?:^|.*;\s*)night\s*\=\s*([^;]*).*$)|^.*$/, "$1") || '0';
        if(night == '0'){
            document.body.classList.remove('night');
        }else if(night == '1'){
            document.body.classList.add('night');
        }
    }
})();

</script>

<script>

function switchModelMode(){
    var model = document.cookie.replace(/(?:(?:^|.*;\s*)model\s*\=\s*([^;]*).*$)|^.*$/, "$1") || '0';
    if(model == '0'){
        document.body.classList.add('model');
        document.cookie = "model=1;path=/"
        console.log('皮肤模式开启');
    }else{
        document.body.classList.remove('model');
        document.cookie = "model=0;path=/"
        console.log('皮肤模式关闭');
    }
}


function switchModelErcyMode(){
    var modelercy = document.cookie.replace(/(?:(?:^|.*;\s*)modelercy\s*\=\s*([^;]*).*$)|^.*$/, "$1") || '0';
    if(modelercy == '0'){
        document.body.classList.add('modelercy');
        document.cookie = "modelercy=1;path=/"
        console.log('皮肤模式开启');
    }else{
        document.body.classList.remove('modelercy');
        document.cookie = "modelercy=0;path=/"
        console.log('皮肤模式关闭');
    }
}

(function(){
    
        var modelercy = document.cookie.replace(/(?:(?:^|.*;\s*)modelercy\s*\=\s*([^;]*).*$)|^.*$/, "$1") || '0';
        if(modelercy == '0'){
            document.body.classList.remove('modelercy');
        }else if(modelercy == '1'){
            document.body.classList.add('modelercy');
        }
    
})();

(function(){
    var model = document.cookie.replace(/(?:(?:^|.*;\s*)model\s*\=\s*([^;]*).*$)|^.*$/, "$1") || '0';
        if(model == '0'){
            document.body.classList.remove('model');
        }else if(model == '1'){
            document.body.classList.add('model');
        }
  
})();
</script>
```
```
<!--主题切换放在页脚-->
<section class="model-3"> 		  
<div class="float-btn-group"> 		     
	<i class="fa fa-cog fa-spin fa-lg "></i> 				
	<div class="btn-list"> 	
		<a href="javascript:void(0);" onclick="switchNightMode()" class="btn-float yellow"><i class="fa fa-moon-o"></i></a> 
		<a href="javascript:void(0);" onclick="switchModelMode()" class="btn-float blue"><i class="fa fa-heart-o"> </i></a>
		<a href="javascript:void(0);" onclick="switchModelErcyMode()"class="btn-float green"><i class="fa fa-heart"></i></a>
		<a href="https://i.cnblogs.com/" class="btn-float pink"><i class="fa fa-user"></i></a>
	</div>
</div>
</section >
```

```
<!-- 主题切换按钮样式 放在页首 -->
<link rel="stylesheet" type="text/css" href="https://example.com/themebtn.css">
<!-- 主题切换按钮样式 -->

```


#### 底部加载音乐播放器

```
<!-- 音乐播放器  放在页首-->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/aplayer@1.10.0/dist/APlayer.min.css">
<link rel="stylesheet" href="https://example.com/DPlayer.min.css">
<div id="aplayer" class="aplayer"  data-id="865331941" data-server="netease" data-type="playlist" data-fixed="true" data-listfolded="true" data-order="random" data-theme="#2D8CF0"></div>
<!-- 音乐播放器end -->

```

```
<!-- 音乐播放器  放在页尾-->
<script src="https://example.com/APlayer.min.js"></script>
<script src="https://unpkg.com/meting@1.2/dist/Meting.min.js"></script>
```



#### 图片灯箱

* 部署

```
<!-- 图片灯箱 放在页首 -->
<link rel="stylesheet" href="https://example.com/zoom.css">
<!-- 图片灯箱 -->
```

```
<!-- 图片灯箱 放在页脚-->
<script src="https://example.com/zoom.js"></script>
```

* 使用

  只需要在`img`标签中 写入 `data-action="zoom"`属性即可。

  ```
  <img src="https:example.png" data-action="zoom">
  ```

#### 加载鼠标动态粒子

```
<!-- 鼠标点击特效 -->
<script src="https://example.com/cursor-effects.js"></script>
<!-- 鼠标点击特效end -->
```

#### 主题文章预览图设置

需要把文章的预览图写在这里。

<img src="https://img.imjad.cn/images/2019/09/16/Snipaste_2019-09-16_17-18-01.png" data-action="zoom">

## 下载地址

* [cnblogs-theme-simple-color](https://github.com/YJLAugus/cnblogs-theme-simple-color)

* 求个小星星!

## 写在最后

如有什么问题可评论在下方，及时更正，再次感谢。
