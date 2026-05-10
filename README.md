# wuzhenjian0125.github.io

武振建的中英双语学术主页。网站默认打开英文版，中文完整版本位于 `/zh/`，两种语言都可以通过导航栏自由切换；旧的 `/en/` 路径保留为英文跳转。

## 结构

- `index.html`、`publications.html`、`projects.html`：英文默认页面
- `zh/`：中文页面
- `en/`：兼容旧链接的英文跳转页面
- `_data/`：双语个人信息、导航与展示配置
- `_publications/`：论文条目
- `_projects/`：研究项目、数据资源、方法能力与合作方向
- `assets/css/global.css`：站点样式

## 本地预览

安装 Ruby 与 Bundler 后可运行：

```bash
bundle install
bundle exec jekyll serve
```

默认访问地址为 `http://127.0.0.1:4000`。
