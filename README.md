# Wang Xinyang / 王心阳 · Personal Homepage

COMP5241 Week 2 作业：一份静态、响应式、中英双语个人主页。

## 在线访问 / Live site

**https://wxy-polyu.github.io/wangxinyang_page/**

仓库：[github.com/wxy-polyu/wangxinyang_page](https://github.com/wxy-polyu/wangxinyang_page)

## Features / 功能

- 单页介绍：首页、关于、教育、技能、实习经历、项目、联系
- 导航栏语言切换：**中文** / **English**
- 所选语言写入 `localStorage`；首次访问默认英文，可在导航栏切换为中文
- 桌面端粘性导航；移动端汉堡菜单
- 项目卡片来自本科博客 [blog.umberk.cn](http://blog.umberk.cn/)，含演示与源码链接
- 个人照片使用根目录 `profile-photo.jpg`；图片缺失时显示姓名首字母 WX

## File structure / 文件结构

```text
.
├── index.html          # 页面结构
├── styles.css          # 版式与组件样式
├── script.js           # 双语、导航、菜单、项目卡片
├── aboutme.md          # 个人资料源文件
├── profile-photo.jpg   # 个人照片
└── README.md
```

样式以 Tailwind CSS（CDN）为主，补充样式写在 `styles.css`。脚本为原生 JavaScript，无后端。

## Run locally / 本地预览

在仓库根目录启动静态服务：

```bash
python3 -m http.server 8765
```

浏览器打开 http://127.0.0.1:8765/

也可直接用浏览器打开 `index.html`。部分浏览器对本地文件限制较严，推荐用本地服务器。

## Bilingual system / 双语说明

可翻译文案集中在 `script.js` 的 `translations` 对象中。`index.html` 通过 `data-i18n` 绑定文案。

- 语言偏好键名：`localStorage.homepage-lang`，值为 `zh` 或 `en`；未保存时默认英文
- 切换语言时会更新页面文字、`document.title` 和 `<html lang>`
- 项目列表由 `script.js` 中的 `PROJECTS` 数组渲染，标题与介绍同样走翻译表

## GitHub Pages

GitHub 仓库链接本身显示的是源代码，不会直接渲染成网站。需要在仓库中开启 Pages：

1. 打开仓库 **Settings → Pages**
2. Source 选择 **Deploy from a branch**
3. Branch 选择 `main`，文件夹选择 `/ (root)`
4. 保存后等待一两分钟，访问 `https://wxy-polyu.github.io/wangxinyang_page/`

若仓库为 private，免费账号可能无法公开 Pages，需改为 public 或确认账号权限。

## Add a project / 新增项目

在 `script.js` 的 `PROJECTS` 中追加一项，并在 `translations.en` / `translations.zh` 中补齐对应文案（`title`、`desc`、`kicker`、`meta`）。

```javascript
{
  id: "example",
  featured: false,
  tags: ["Vue 3"],
  demo: "https://example.com",
  source: "https://github.com/Umberk/example",
}
```

没有公开演示或仓库时，把 `demo` / `source` 设为 `null` 即可，卡片上不会生成对应按钮。

## Links / 链接

- 在线主页 / Live site: https://wxy-polyu.github.io/wangxinyang_page/
- Email: wangxinyang040129@gmail.com
- Personal blog: http://blog.umberk.cn/
- Personal GitHub: https://github.com/Umberk
- PolyU GitHub: https://github.com/wxy-polyu
