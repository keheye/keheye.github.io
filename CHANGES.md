# 网站简化说明

## 已完成的修改

### 1. 主页面改造 ✅
- 将 `_pages/about.md` 改造为完整的单页简历
- 设置 `author_profile: false` 禁用侧边栏
- 添加了所有简历内容:教育、经历、出版物、奖项、项目、技能
- 添加了居中的标题和联系信息

### 2. 删除不需要的内容 ✅
删除的目录:
- `_talks/` - 演讲
- `_teaching/` - 教学
- `_portfolio/` - 作品集
- `_posts/` - 博客文章
- `_drafts/` - 草稿
- `markdown_generator/` - Markdown 生成器
- `talkmap/` - Talk 地图

删除的页面文件:
- cv.md, talks.html, teaching.html, publications.html
- portfolio.html, talkmap.html, year-archive.html
- tag-archive.html, category-archive.html
- 以及其他示例页面

### 3. 配置文件简化 ✅

#### _config.yml
- 更新了网站标题为 "Kehe Ye / 叶可贺"
- 更新了作者信息和联系方式
- 禁用了不需要的集合 (talks, teaching, portfolio, posts)
- 禁用了评论功能
- 禁用了 RSS feed
- 设置所有页面的 `author_profile: false`

#### _data/navigation.yml
- 清空了所有导航项
- 设置 `main: []` 完全隐藏导航栏

### 4. 样式优化 ✅
创建了 `_sass/_custom.scss`:
- 隐藏导航栏 (.masthead)
- 隐藏侧边栏 (.sidebar)
- 内容区域全宽显示
- 内容居中,最大宽度 900px
- 简化了页脚
- 添加了打印友好样式

### 5. Footer 简化 ✅
- 移除了社交媒体链接
- 移除了 "Powered by" 信息
- 只保留简单的版权声明

### 6. README 更新 ✅
- 更新了项目说明
- 添加了本地运行指南
- 说明了网站结构

## 保留的内容

✅ `_publications/` - 论文发表 (只有 FieldGen 一篇)
✅ `_pages/about.md` - 主页/简历
✅ `_data/cv.json` - 结构化简历数据
✅ `_config.yml` - 网站配置
✅ `assets/` - 静态资源
✅ `_includes/` - 模板组件
✅ `_layouts/` - 页面布局
✅ `_sass/` - 样式文件

## 最终效果

现在的网站是一个:
- ✅ 单页简历网站
- ✅ 没有顶部导航栏
- ✅ 没有侧边栏
- ✅ 干净简洁的布局
- ✅ 居中显示,最大宽度 900px
- ✅ 包含所有必要的简历信息
- ✅ 适合打印和在线查看

## 如何查看

1. 本地预览 (简单方式):
   ```bash
   cd /home/agiuser/Application/keheye.github.io
   python3 -m http.server 8000
   ```
   访问: http://localhost:8000/_pages/about.html

2. Jekyll 完整预览 (推荐):
   ```bash
   sudo apt install ruby-dev ruby-bundler nodejs
   bundle install
   bundle exec jekyll serve
   ```
   访问: http://localhost:4000

3. 推送到 GitHub Pages:
   ```bash
   git add .
   git commit -m "Simplify to single-page CV"
   git push
   ```
   访问: https://keheye.github.io
