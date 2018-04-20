
### 从零开始

准备好开始了吗？从零开始创建你自己的博客。😅

### 创建一个库

<img src="https://ricebai.github.io/img/posts/github-blog/create_repository.jpg" />

在 GitHub 上创建一个存储库，用于存放你的博客项目

在根目录创建一个 index.html 文件用于首页。

打开浏览器，输入 `github name`.github.io

（如：我的 github 名字是 ricebai ，访问路径就是 [ricebai.github.io](https://ricebai.github.io)）

进行到这里，你的博客第一个简易的页面就创建出来了，将会在页面看到你编写 index.html 内容。👍

如果无法访问，检查你的 `github name` 是否正确。

### 集成 jekyll 网络结构

jekyll 目录结构
<pre><code>├── _config.yml
├── _drafts
|   ├── begin-with-the-crazy-ideas.textile
|   └── on-simplicity-in-technology.markdown
├── _includes
|   ├── footer.html
|   └── header.html
├── _layouts
|   ├── default.html
|   └── post.html
├── _posts
|   ├── 2007-10-29-why-every-programmer-should-play-nethack.textile
|   └── 2009-04-26-barcamp-boston-4-roundup.textile
├── _data
|   └── members.yml
├── _site
├── img
└── index.html
</code></pre>

在 `_posts` 目录下创建你的博客文件，但文件名称一定要用英文，不然后续集成的 `Gitalk` 评论插件无法自动创建目录。💡

我们可以引用别人的炫酷的主题创建属于自己的博客

进入我的仓库，选择 `settings` -> `Options`：

<img src="https://ricebai.github.io/img/posts/github-blog/choose_theme.jpg" />

可以参考：[GitHub Pages](https://pages.github.com)

### 集成 Gitalk 评论插件

可以参考：[BY Blog 博客添加 Gitalk 评论插件](http://qiubaiying.top/2017/12/19/为博客添加-Gitalk-评论插件/)
