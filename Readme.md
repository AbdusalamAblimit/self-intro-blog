
此个人博客的搭建过程参考了：https://blog.cuijiacai.com/blog-building/
下面的一些说明也引用了该文。

各部分的含义：

    _config.yml
        为全局配置文件，网站的很多信息都在这里配置，比如说网站名称，副标题，描述，作者，语言，主题等等。具体可以参考官方文档：https://hexo.io/zh-cn/docs/configuration.html。
    scaffolds
        骨架文件，是生成新页面或者新博客的模版。可以根据需求编辑，当hexo生成新博客的时候，会用这里面的模版进行初始化。
    source
        这个文件夹下面存放的是网站的markdown源文件，里面有一个_post文件夹，所有的.md博客文件都会存放在这个文件夹下。现在，你应该能看到里面有一个hello-world.md文件。
    themes
        网站主题目录，hexo有非常丰富的主题支持，主题目录会存放在这个目录下面。
        我们后续会以默认主题来演示，更多的主题参见：https://hexo.io/themes/

