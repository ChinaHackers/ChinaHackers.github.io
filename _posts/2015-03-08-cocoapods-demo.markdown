

<h1>CocoaPods安装使用心得，分享给墙内的朋友们</h1>


<h2>前言</h2>

<p>CocoaPods是一个负责管理iOS项目中第三方开源代码的工具。</p>

<p>二、安装
由于网上的教程基本都大同小异，但细节之处还不是很完善，所以借机会在这里补充下：
注：要使用CocoaPods，那就要下载安装它，而下载安装CocoaPods需要Ruby环境</p>

<h2>1.Ruby环境搭建</h2>

<p>当前安装环境为Mac Pro 10.11.1。Mac  OS本身自带Ruby，但还是更新一下保险，因为升级了系统之后,可能会出现一些意想不到的情况,最好还是更新一下Ruby。</p>

<ul><li><p>查看下当前ruby版本：打开终端输入 ruby -v（确实安装了，不过iOS9使用https协议替换http协议,所以以前挂靠在淘宝下ruby的源的路径也要修改下，顺便更新下ruby）</p><p>   

{% highlight swift %}

<code> CYdediannao:~ lcy$  ruby -v  </p>
 ruby 2.0.0p645 (2015-04-13 revision 50299) [universal.x86_64-darwin15]`&lt;/pre&gt;
 <code>
 </p>
{% endhighlight %}
 
 </li><li><p>淘宝已经停止基于 HTTP 协议的镜像服务, 请在配置中使用 HTTPS 协议代替</p>

{% highlight swift %}

CYdediannao:~ lcy$ gem sources - l
<strong>* CURRENT SOURCES </strong>* 

http://ruby.taobao.org/

CYdediannao:~ lcy$ gem sources --add https://ruby.taobao.org/ --remove http://ruby.taobao.org/</p>
https://ruby.taobao.org/ added to sources </p>
http://ruby.taobao.org/ removed from sources

{% endhighlight %}
<p>
<p></li><li><p>gem sources -l  （用来检查使用替换镜像位置成功，然后升级ruby

{% highlight swift %} <p>
<code>CYdediannao:~ lcy$ sudo gem install rails</code> <p>
{% endhighlight %}


或者是 <code>CYdediannao:~ lcy$ sudo gem update --system</code></p>

<h2>2.下载安装CocoaPods</h2>

{% highlight swift %}
<code>CYdediannao:~ lcy$ sudo gem install cocoapods</code>

</p><h3>出现的错误###：原因是该文件夹没有修改的权限</h3>

<code>CYdediannao:~ lcy$ sudo gem install cocoapods <p>
Fetching: nap-1.0.0.gem (100%)<p>
Successfully installed nap-1.0.0 <p>
Fetching: molinillo-0.4.0.gem (100%) <p>
Successfully installed molinillo-0.4.0 <p>
Fetching: cocoapods-trunk-0.6.4.gem (100%) <p>
Successfully installed cocoapods-trunk-0.6.4 <p>
Fetching: cocoapods-try-0.5.1.gem (100%) <p>
Successfully installed cocoapods-try-0.5.1 <p>
Fetching: cocoapods-stats-0.6.2.gem (100%) <p>
Successfully installed cocoapods-stats-0.6.2 <p>
Fetching: cocoapods-search-0.1.0.gem (100%) <p>
Successfully installed cocoapods-search-0.1.0 <p>
Fetching: cocoapods-downloader-0.9.3.gem (100%) <p>
Successfully installed cocoapods-downloader-0.9.3 <p>
Fetching: xcodeproj-0.28.2.gem (100%) <p>
ERROR:  While executing gem ... (Errno::EPERM)
    Operation not permitted - /usr/bin/xcodeproj</code></p>
    {% endhighlight %}

   <h3>10.11以上系统使用命令： sudo gem install -n /usr/local/bin cocoapods</h3>
    
   {% highlight swift %} <p>
   <code>CYdediannao:~ lcy$ sudo gem install -n /usr/local/bin cocoapods
Password: <p>
Successfully installed xcodeproj-0.28.2 <p>
Fetching: cocoapods-core-0.39.0.gem (100%) <p>
Successfully installed cocoapods-core-0.39.0 <p>
Fetching: cocoapods-0.39.0.gem (100%) <p>
Successfully installed cocoapods-0.39.0 <p>
Parsing documentation for xcodeproj-0.28.2 <p>
Installing ri documentation for xcodeproj-0.28.2 <p>
Parsing documentation for cocoapods-core-0.39.0 <p>
Installing ri documentation for cocoapods-core-0.39.0 <p>
Parsing documentation for cocoapods-0.39.0 <p>
Installing ri documentation for cocoapods-0.39.0 <p>
3 gems installed</code>&lt;/pre&gt;</p>

{% endhighlight %}

<h4>3.使用命令 pod search AFNetworking 查找某一个库，看cocoapods有没有安装好，搜索结果如下，已经安装好了cocoa pods</h4><p>
<p>
{% highlight swift %} <p>
-> AFNetworking (2.6.0) <p>
   A delightful iOS and OS X networking framework. <p>
   pod &#39;AFNetworking&#39;, &#39;~&amp;gt; 2.6.0&#39; <p>
   - Homepage: https://github.com/AFNetworking/AFNetworking <p>
   - Source:   https://github.com/AFNetworking/AFNetworking.git <p>
   - Versions: 2.6.0, 2.5.4, 2.5.3, 2.5.2, 2.5.1, 2.5.0, 2.4.1, 2.4.0, 2.3.1, <p>
   2.3.0, 2.2.4, 2.2.3, 2.2.2, 2.2.1, 2.2.0, 2.1.0, 2.0.3, 2.0.2, 2.0.1, 2.0.0,<p>
   2.0.0-RC3, 2.0.0-RC2, 2.0.0-RC1, 1.3.4, 1.3.3, 1.3.2, 1.3.1, 1.3.0, 1.2.1,<p>
   1.2.0, 1.1.0, 1.0.1, 1.0, 1.0RC3, 1.0RC2, 1.0RC1, 0.10.1, 0.10.0, 0.9.2,<p>
   0.9.1, 0.9.0, 0.7.0, 0.5.1 [master repo] - 2.6.0, 2.5.4, 2.5.3, 2.5.2, 2.5.1,<p>
   2.5.0, 2.4.1, 2.4.0, 2.3.1, 2.3.0, 2.2.4, 2.2.3, 2.2.2, 2.2.1, 2.2.0, 2.1.0,<p>
   2.0.3, 2.0.2, 2.0.1, 2.0.0, 2.0.0-RC3, 2.0.0-RC2, 2.0.0-RC1, 1.3.4, 1.3.3,<p>
   1.3.2, 1.3.1, 1.3.0, 1.2.1, 1.2.0, 1.1.0, 1.0.1, 1.0, 1.0RC3, 1.0RC2, 1.0RC1,<p>
   0.10.1, 0.10.0, 0.9.2, 0.9.1, 0.9.0, 0.7.0, 0.5.1 [master-1 repo]<p>
   - Subspecs:<p>
     - AFNetworking/Serialization (2.6.0) <p>
     - AFNetworking/Security (2.6.0) <p>
     - AFNetworking/Reachability (2.6.0) <p>
     - AFNetworking/NSURLConnection (2.6.0) <p>
     - AFNetworking/NSURLSession (2.6.0) <p>
     - AFNetworking/UIKit (2.6.0)</p>

->AFNetworking+AutoRetry (0.0.5) <p>
   Auto Retries for AFNetworking requests <p>
   pod &#39;AFNetworking+AutoRetry&#39;, &#39;~&amp;gt; 0.0.5&#39; <p>
   - Homepage: https://github.com/shaioz/AFNetworking-AutoRetry <p>
   - Source:   https://github.com/shaioz/AFNetworking-AutoRetry.git <p>
   - Versions: 0.0.5, 0.0.4, 0.0.3, 0.0.2, 0.0.1 [master repo] - 0.0.5, 0.0.4, <p>
   0.0.3, 0.0.2, 0.0.1 [master-1 repo]</p><p>-&amp;gt; AFNetworking+Ext (1.2.1) <p>
   AFNetworking的封装, 并提供一个 UIImageView+DYLoading  cache in fileSystem+memory <p>
   pod &#39;AFNetworking+Ext&#39;, &#39;~&amp;gt; 1.2.1&#39; <p>
   - Homepage: https://github.com/junhaiyang/AFNetworkingExt<p>
   - Source:   https://github.com/junhaiyang/AFNetworkingExt.git <p>
   - Versions: 1.2.1, 1.2, 1.1, 1.0, 0.5, 0.4, 0.3 [master repo] - 1.2.1, 1.2, <p>
   1.1, 1.0, 0.5, 0.4, 0.3 [master-1 repo]<p>
   - Subspecs:<p>
     - AFNetworking+Ext/Base (1.2.1)<p>
     - AFNetworking+Ext/AFCustomRequestOperation (1.2.1)<p>
     - AFNetworking+Ext/AFDownloadRequestOperation (1.2.1)<p>
     - AFNetworking+Ext/AFTextResponseSerializer (1.2.1)<p>
     - AFNetworking+Ext/example (1.2.1)<p>
     - AFNetworking+Ext/UIKit (1.2.1)<p>
     - AFNetworking+Ext/UIKit/UIImageView+DYLoading (1.2.1)</p>
    				
   <h5>还有很大篇幅的结果，此处省略。。。##</h5>

{% endhighlight %}

</h5><h2>4.cocoapods的使用</h2>

</li><li><p>新建一个项目，名字podsTest项目

<img alt="" src="http://upload-images.jianshu.io/upload_images/830888-25c7ce2edc1537e6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240"/>


</li><li><p>打开项目所在的文件夹，在终端敲入 cd 将文件夹拖拽到终端 <p>
或者用cd打开项目所在文件夹（注意：包含podsTest文件夹、podsTest.xcodeproj、podsTestTest、podsTestUITests的那个总目录）如图：

</p>
<img alt="" src="http://upload-images.jianshu.io/upload_images/830888-135856a82cc057d3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240"/>
</p>


<img alt="" src="http://upload-images.jianshu.io/upload_images/830888-bc6bbedf65e2da2b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240"/>
</li><li><p>建立Podfile（配置文件）
</p>
1.接着上一步，终端输入 vim Podfile
</p>
<img alt="" src="http://upload-images.jianshu.io/upload_images/830888-ff9367af4eea800b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240"/>
<p>
2.键盘输入 i，进入编辑模式

<p>
<img alt="" src="http://upload-images.jianshu.io/upload_images/830888-82d38c7fcfc4d8c0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240"/>
</p>


3.内容按这个格式输入
</p>
　platform :ios, &#39;7.0&#39;</p>
　pod &#39;MBProgressHUD&#39;, &#39;~&amp;gt; 0.9.1&#39;</p>
　pod &#39;ASIHTTPRequest&#39;, &#39;~&amp;gt; 1.8.2&#39;</p>
　pod &#39;SDWebImage&#39;, &#39;~&amp;gt; 3.7.3&#39;</p>
　<p>注意：　如果你不知道这些框架目前的版本是，可以使用命令pod search +框架名称查看 相应的信息</p><p>
　
<img alt="" src="http://upload-images.jianshu.io/upload_images/830888-31adb37f17d235b0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240"/>

</p><p> 4.然后按Esc，并且输入 shift +“ ：”号进入vim命令模式，然后在冒号后边输入wq 按回车键，保存并且退出。
 </p>5.结果如下图：
 </p><p>
<img alt="" src="http://upload-images.jianshu.io/upload_images/830888-1f1a82c28b6110c9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240"/>

</p><p>6.发现podTest项目总目录中多一个Podfile文件</p><p>
<img alt="" src="http://upload-images.jianshu.io/upload_images/830888-7aadbe1cfd34ad7e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240"/>

</p><p>7.激动人心的时刻到了：确定终端cd到项目总目录，然后输入 pod install，等待一会，框架安装好了如图所示，多出了3个文件夹/文件夹。</p><p>
<img alt="" src="http://upload-images.jianshu.io/upload_images/830888-08526c1690c9f975.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240"/>


</p><h3>注意：</h3><p>现在打开项目不是点击 podTest.xodeproj了，而是点击 podsTest.xcworkspace</p><p>

<img alt="" src="http://upload-images.jianshu.io/upload_images/830888-374b5624ae6ecf9c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240"/>


</p><h2>5.cocoaPods使用心得</h2></li><li><p>最近使用CocoaPods来添加第三方类库，无论是执行pod install还是pod update都卡在了Analyzing dependencies不动 原因在于当执行以上两个命令的时候会升级CocoaPods的spec仓库，加一个参数可以省略这一步，命令如下：   
</p><code>pod install --verbose --no-repo-update

</p><code>pod update --verbose --no-repo-update</code>

$ pod install只会按照Podfile的要求来请求类库，如果类库版本号有变化，那么将获取失败。但是 $ pod update会更新所有的类库，获取最新版本的类库。每次用$ pod update就行。


<p></li><li>安装一个xcode插件管理工具，<a href="http://alcatraz.io">地址</a> 目前还不支持XCode7
</p>

<p>在终端中执行
<code>curl -fsSL https://raw.github.com/supermarin/Alcatraz/master/Scripts/install.sh | sh</code>
<p>
安装完了打开xcode-&amp;gt;window-&amp;gt;package manger 搜cocoapods安装，方便操作。</li><li>工程在模拟器上编译报错，不支持i386，Cocoapods确实还不支持64位模拟器，<a href="http://stackoverflow.com/questions/19213782/undefined-symbols-for-architecture-arm64">解决办法：</a>
</p>

其实就2条：
<p>1.build active architecture only 在debug的时候设置成YES，不要在release的时候用模拟器
<p>2.other linker flags 加一个 $(inherited)
<p>用到svn,git多人协作的话，Pods/这个文件夹不要上传，例如：
.../Pods/Pods.xcodeproj  ...Pods/Target Support Files/这些每次编译都会改动从而引起合并代码的时候冲突</p><p><a href="http://www.cocoachina.com/bbs/read.php?tid-277900.html">心得内容来源</a></p>

<h2>6.cocoaPods使用常见错误汇总：</h2>
</li><li><p>pod install 时出现以下错误，错误原因是在vim Podfile 时，输入命令前面带有空格导致的，把空格去掉就好了</p>

{% highlight swift %}
<code>错误写法：</p>
　platform :ios, &#39;7.0&#39;</p>
　pod &#39;MBProgressHUD&#39;, &#39;~&amp;gt; 0.9.1&#39;</p>
　pod &#39;ASIHTTPRequest&#39;, &#39;~&amp;gt; 1.8.2&#39;</p>
　pod &#39;SDWebImage&#39;, &#39;~&amp;gt; 3.7.3&#39;</p>
提示错误：
<p>
[!] Invalid </code>Podfile<code> file: undefined method </code>　pod&#39; for #&amp;lt;Pod::Podfile:0x007ff3f9a45a48&amp;gt;. Updating CocoaPods might fix the issue.</p><p>正确写法：命令前面不留空格</p>

platform :ios, &#39;7.0&#39;</p>
pod &#39;MBProgressHUD&#39;, &#39;~&amp;gt; 0.9.1&#39;</p>
pod &#39;ASIHTTPRequest&#39;, &#39;~&amp;gt; 1.8.2&#39;</p>
pod &#39;SDWebImage&#39;, &#39;~&amp;gt; 3.7.3&#39;</p>

{% endhighlight %}

<h3>7 使用CocoaPods来管理Objective-c的类库，非常方便。但是有一个小问题，当我在xcode输入import关键字的时候，没有自动联想补齐代码的功能，需要手工敲全了文件名，难以适应。</h3></p>

{% highlight swift %}

</p><code>在stackoverflow上找到了解决办法:</p>
1.Go to the Target &amp;gt; \”Build Settings\” tab and find the \”User Header Search Paths\” setting.</p>

2.Set this to \”$(BUILT<em>PRODUCTS</em>DIR)\” and check the \”Recursive\” check box.</p>

Now the built target will search the workspace’s shared build directory to locate the linkable header files.</p>

<b><p>简单说就是这么几步:
<p>
1.选择Target -&amp;gt; Build Settings 菜单，找到\”User Header Search Paths\”设置项
<p>
2.新增一个值$(BUILT<em>PRODUCTS</em>DIR)，并且选择\”Recursive\”，这样xcode就会在项目目录中递归搜索文件
自动补齐功能马上就好使了。</p></b>
{% endhighlight %}

