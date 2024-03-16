# 项目是用来做什么的?
获取 GitHub 的用户贡献信息

此项目 fork 自 [python_github_calendar_api](https://github.com/Zfour/python_github_calendar_api)仓库，原理通过 Python 获取 GitHub 的用户贡献信息，你可以部署到 Vercel 上作为 API 使用。

如果你有 Hexo 博客，可以搭配使用 hexo-get-github-contribute 插件在前端渲染贡献热力图。(此插件是参考[fork作者](https://github.com/Zfour/python_github_calendar_api)所修改的)

# 如何访问?
部署后, 通过基地址+/api?user=Yikoutian1</br>
例如: https://xxxx.vercel.app/api?user=Yikoutian1
> 你可以选择自定义域名绑定到vercel

# 如何使用
```
npm i hexo-get-github-contribute --save
```
如果你是hexo相关的主题, 那么在根目录配置文件 即_config.yml
添加如下配置
```yaml
# github贡献图
githubcalendar:
    enable: true
    priority: 3
    enable_page: /
    user: user=yikoutian1
    layout:
        type: id
        name: recent-posts
        index: 0
    githubcalendar_html: '<div class="recent-post-item" style="width:100%;height:auto;padding:10px;"><div id="github_loading" style="height:100%;display: flex;align-items: center;justify-content: center;"><svg style="height:50px" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"  viewBox="0 0 50 50" style="enable-background:new 0 0 50 50" xml:space="preserve"><path fill="#d0d0d0" d="M25.251,6.461c-10.318,0-18.683,8.365-18.683,18.683h4.068c0-8.071,6.543-14.615,14.615-14.615V6.461z" transform="rotate(275.098 25 25)"><animateTransform attributeType="xml" attributeName="transform" type="rotate" from="0 25 25" to="360 25 25" dur="0.6s" repeatCount="indefinite"></animateTransform></path></svg></div><div id="github_container"></div></div>'
    pc_minheight: 248px
    mobile_minheight: 0px
    color: "['#ebedf0', '#fdcdec', '#fc9bd9', '#fa6ac5', '#f838b2', '#f5089f', '#c4067e', '#92055e', '#540336', '#48022f', '#30021f']"
    #api: api更换为你的api地址,后续拼接步骤为:  例如我们的字符串为`user=y`,那么api=https://github-contribute.calyee.top/api?user=y
    api: https://github-contribute.calyee.top/api
    calendar_js: https://cdn.jsdelivr.net/npm/hexo-get-github-contribute@1.0.1/hexo_githubcalendar.js
    plus_style: ""
```
对于githubcalendar.user处,我们添加的value为`user=yikoutian1`, 把等于号后面的昵称更换成你的即可
