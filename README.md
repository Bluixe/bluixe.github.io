# Academic homepage

基于 [Minimal Light](https://github.com/yaoyao-liu/minimal-light) 官方纯 HTML 版本的学术个人主页。

- 在线地址：<https://bluixe.github.io/>
- 仓库：<https://github.com/Bluixe/bluixe.github.io>
- 当前内容为占位示例，尚未填写真实个人资料、论文或履历。
- 保留 Minimal Light 的双栏布局、论文展示和系统深浅色适配；样式和图片均保存在仓库内。

## 修改个人资料

所有页面内容均在 `index.html` 中，并用中文注释标出编辑位置。

| 要修改的内容 | 文件与位置 |
| --- | --- |
| 网页标题与搜索摘要 | `index.html` 的 `<title>` 和 description 元信息 |
| 姓名、身份、单位、邮箱 | `index.html` 的「个人资料」注释下方 |
| GitHub、Scholar、CV 链接 | `index.html` 的「个人链接」注释下方 |
| 简介、研究方向、新闻 | `index.html` 中对应的小标题下方 |
| 论文标题、作者、发表信息和链接 | `index.html` 中的「论文列表」；复制一个 `<li>` 即可增加论文 |
| 学术服务和联系信息 | `index.html` 中对应的小标题下方 |
| 头像 | 替换 `assets/img/avatar.svg`，或在 `index.html` 中改为自己的 JPG/PNG 路径 |
| 论文配图 | 替换 `assets/img/paper-placeholder.svg`，或修改论文的图片路径 |
| 网站小图标 | `assets/img/favicon.svg` |
| 自定义样式 | `assets/css/site.css` |

Scholar 和 CV 尚未配置，因此目前显示为普通占位文字。添加资料后，将相应的 `<span>` 改为 `<a href="实际链接">…</a>`。CV PDF 可以放在 `assets/files/` 后链接到该文件。论文的 PDF、Code、Project 按钮同理，未添加真实链接前保持占位状态。

## 本地预览

页面使用模板官方提供的纯 HTML 方式，不需要 Ruby、Jekyll 或构建步骤。独立 conda 环境 `homepage` 只用于本地预览和检查，不影响 GitHub 上的托管。

首次配置：

```powershell
conda env create -f environment.yml
```

在本仓库目录启动预览：

```powershell
conda run --no-capture-output -n homepage python -m http.server 4000 --bind 127.0.0.1
```

打开 <http://127.0.0.1:4000/>，刷新浏览器即可查看修改。按 `Ctrl+C` 停止预览。

## 发布更新

GitHub Pages 使用 `main` 分支的根目录；`.nojekyll` 让 GitHub 直接发布静态文件。保持 Custom domain 留空即可继续使用免费地址。

```powershell
git add index.html assets README.md
git commit -m "Update academic profile"
git push origin main
```

推送后，可在仓库的 Actions 或 Settings → Pages 查看发布结果。

## 模板来源

上游版本、许可及本地调整见 [THIRD_PARTY.md](THIRD_PARTY.md)。
