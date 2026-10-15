# Academic homepage

基于 [Minimal Light](https://github.com/yaoyao-liu/minimal-light) 官方纯 HTML 版本的学术个人主页。

- 在线地址：<https://bluixe.github.io/>
- 仓库：<https://github.com/Bluixe/bluixe.github.io>
- 已根据最新简历补充姓名、学术邮箱、研究简介、5 篇论文和 2 段教育经历；论文保留完整作者，并加粗 Wenhao Zhang。
- 本次资料基准为 2026-10-15 的简历版本 `c4459dd`。简历源文件保存在本地忽略目录，不随主页发布。
- 保留 Minimal Light 的双栏布局、论文展示和系统深浅色适配；样式和图片均保存在仓库内。

## 修改个人资料

所有页面内容均在 `index.html` 中，并用中文注释标出编辑位置。

| 要修改的内容 | 文件与位置 |
| --- | --- |
| 网页标题与搜索摘要 | `index.html` 的 `<title>` 和 description 元信息 |
| 姓名、身份、单位、邮箱 | `index.html` 的「个人资料」注释下方 |
| GitHub、Scholar、CV 链接 | `index.html` 的「个人链接」注释下方 |
| 简介、研究方向、教育经历、新闻 | `index.html` 中对应的小标题下方 |
| 论文标题、作者、发表信息和链接 | `index.html` 中的「论文列表」；复制一个 `<li>` 即可增加论文 |
| 联系信息 | `index.html` 的 Contact 下方；有学术服务信息后可新增栏目 |
| 头像 | 替换 `assets/img/avatar.svg`，或在 `index.html` 中改为自己的 JPG/PNG 路径 |
| 论文展示 | 当前使用会议／期刊及年份标记；之后可按需要增加论文配图 |
| 网站小图标 | `assets/img/favicon.svg` |
| 自定义样式 | `assets/css/site.css` |

个人链接目前提供 GitHub 和学术邮箱。添加 Scholar 主页或公开版 CV 后，可以在 `profile-links` 中增加链接；CV PDF 可以放在 `assets/files/`。论文条目已链接对应论文页面、PDF 和已核实的代码仓库。

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
