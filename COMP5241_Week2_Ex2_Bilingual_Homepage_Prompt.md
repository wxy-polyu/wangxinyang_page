# COMP5241 Week 2 Exercise 2：中英文个人主页提示词

> 使用方式：先在 GitHub Codespace 的 repository 根目录创建 `aboutme.md`，粘贴第 1 部分；之后打开 GitHub Copilot Chat，切换到 Agent Mode，粘贴第 2 部分。

## 1. 创建 `aboutme.md`

把下面内容完整粘贴到 repository 根目录的 `aboutme.md`。

```markdown
# Wang Xinyang / 王心阳

## About Me / 个人简介

### English

Wang Xinyang is an MSc student in Information Technology at The Hong Kong Polytechnic University. Wang Xinyang has hands-on frontend development internship experience at Jinmen Finance (进门财经). Interests include frontend engineering, web application development, and practical software products.

### 中文

王心阳目前是香港理工大学（The Hong Kong Polytechnic University）信息技术（Information Technology）专业硕士研究生。他曾在进门财经担任前端开发实习生，关注前端工程、Web 应用开发以及实用型软件产品。

Email: wangxinyang040129@gmail.com

![Profile Photo](profile-photo.jpg)

## Education / 教育经历

### English

- Master of Science in Information Technology, The Hong Kong Polytechnic University

### 中文

- 香港理工大学，信息技术专业硕士

## Skills / 技能

- Frontend: Vue 3, React, JavaScript, HTML, CSS
- Development tools: Git, GitHub, VS Code
- API integration and frontend-backend data interaction
- Responsive web development for PC and mobile H5/App
- Shared component development and maintenance

## Internship Experience / 实习经历

### English

**Frontend Development Intern, Jinmen Finance (进门财经)**

- Worked on the frontend of financial terminal web products, including the BRM operations backend and roadshow platform, covering both PC and mobile H5/App.
- Built business components and integrated backend APIs using Vue 3, React, and JavaScript.
- Independently delivered frontend work for the company's new official website, the user reward feature ("Niubi" / 牛币), roadshow attendee follow-up, and trial account verification and activation.
- Added and optimized reusable components for the company component library, `comein-ui-plus`.
- Collaborated on requirement iterations, page self-testing, and production bug fixes using Git-based workflows.

**Internship Evaluation**

During the internship, Wang Xinyang served as a frontend development intern. During this period, Wang Xinyang was diligent, responsible, and proactive in asking mentors for help when needed. Wang Xinyang thought carefully and completed assigned tasks on time and to a high standard. Overall performance was excellent. The code was well structured, and Wang Xinyang demonstrated strong teamwork and independent problem-solving abilities.

### 中文

**进门财经，前端开发实习生**

- 参与公司金融终端 Web 页面开发，包括 BRM 运营后台及路演平台，覆盖 PC 端和移动端 H5/App。
- 熟练运用 Vue 3、React、JavaScript 搭建业务组件，并对接后端 API 完成数据交互。
- 独立承担新版官网页面开发、用户牛币、路演参会用户跟进、试用账号认证开通等需求的前端实现。
- 为公司组件库 `comein-ui-plus` 新增及优化多个通用组件。
- 配合团队完成需求迭代、页面自测与线上 bug 修复，使用 Git 协同开发。

**实习鉴定**

该同学在实习期间担任前端开发实习生，工作勤奋踏实、认真负责，遇到不懂的问题能虚心向前辈请教，善于思考，能保质保量完成所分配的工作任务。整体表现优秀，代码规范，具备良好的团队协作意识和独立解决问题的能力，能够胜任前端开发相关工作。

## Projects / 项目

### Personal Blog / 个人博客

- Website: http://blog.umberk.cn/
- Description: A personal blog created during undergraduate study, containing personal articles and technical content.

> More projects will be added later. Do not invent additional projects or achievements now.

## Links / 链接

- Personal Blog: http://blog.umberk.cn/
- Personal GitHub: https://github.com/Umberk
- PolyU GitHub: https://github.com/wxy-polyu
```

如果暂时还没有上传照片，可以先准备一个名为 `profile-photo.jpg` 的图片并上传到 repository 根目录；如果没有照片，就让网站显示姓名首字母作为 fallback，不要生成虚假的人物照片。

## 2. 粘贴给 GitHub Copilot Agent Mode 的完整提示词

```text
Read aboutme.md. Use the info and images inside it to create a professional personal homepage. Generate index.html, styles.css, and script.js. Use Tailwind CSS and ensure the design is responsive.

Additional requirements:

1. Build a polished, professional, single-page personal portfolio for Wang Xinyang.
2. The entire website must support both Simplified Chinese and English. Add a clearly visible language switch in the navigation bar with two options: "中文" and "English".
3. Store all translatable website text in a JavaScript translation object in script.js. Use data-i18n keys in index.html so switching languages updates all visible content, including the page title, navigation, headings, buttons, descriptions, project cards, and footer.
4. Save the selected language in localStorage. On first visit, choose Chinese when the browser language starts with "zh"; otherwise use English. Update the <html lang> attribute when the language changes.
5. The homepage must include these sections:
   - Hero section with the full name, current MSc Information Technology status at The Hong Kong Polytechnic University, a concise introduction, and contact buttons.
   - About Me.
   - Education.
   - Skills, grouped into frontend, tools, and API integration.
   - Internship Experience at Jinmen Finance (进门财经), including the responsibilities and internship evaluation from aboutme.md.
   - Projects. For now, show only the Personal Blog at http://blog.umberk.cn/. Create a reusable project-card structure so more projects can be added later, but do not invent any additional projects or achievements.
   - Contact and Links, including wangxinyang040129@gmail.com, https://github.com/Umberk, https://github.com/wxy-polyu, and http://blog.umberk.cn/.
6. Use all information exactly and truthfully. Do not invent a degree, company, role, project, award, skill, location, or date that is not present in aboutme.md.
7. Use profile-photo.jpg as the profile image. If the image is missing or fails to load, show a clean initials-based fallback for "WX" instead of a broken image or fake person.
8. Use a modern professional visual style with strong typography, generous spacing, accessible contrast, subtle animations, and a restrained color palette. Avoid an overly generic purple-gradient design.
9. Make the navigation bar sticky. All navigation links must scroll smoothly to the correct section. Ensure there is an obvious active or hover state.
10. Make the site fully responsive on desktop, tablet, and mobile. Text and buttons must not overlap or overflow. Use a mobile navigation menu if needed, and make sure it opens and closes correctly.
11. Use semantic HTML, accessible labels, keyboard-friendly controls, alt text, focus states, and sufficient color contrast.
12. Use only vanilla JavaScript in script.js. Do not use a backend, database, authentication, framework router, or external API.
13. All external links must open the correct URL and use target="_blank" with rel="noopener noreferrer" where appropriate.
14. Keep index.html, styles.css, and script.js clearly organized. Do not put all code into index.html.
15. After implementation, verify every link, button, language toggle, navigation item, and mobile menu interaction. Fix any broken behavior before finishing.
16. At the end, summarize the files created and explain how the bilingual system and localStorage language preference work.
```

## 3. 第一版完成后建议再发一次

```text
Audit the bilingual personal homepage as a strict QA reviewer. Test both Chinese and English, the language switch, localStorage persistence, mobile menu, every navigation link, every external link, the profile-photo fallback, keyboard navigation, and responsive layouts at mobile, tablet, and desktop widths. Fix every issue you find. Confirm that no additional project or achievement has been invented. Then summarize the fixes and explain how I can add a new project card later.
```
