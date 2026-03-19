# GitHub 部署指南

## 当前状态

✅ 项目结构已创建
✅ 课程文件已复制
✅ Git仓库已初始化
✅ 代码已提交到本地

## 下一步操作

由于系统没有安装GitHub CLI工具，需要手动完成以下步骤：

### 1. 在GitHub上创建仓库

1. 访问 https://github.com/new
2. 仓库名称：`sql-mysql-course`
3. 描述：SQL与MySQL数据库课程 - 系统讲解SQL语言和MySQL数据库的核心概念与实际应用
4. 选择 **Public** （公开仓库）
5. **不要**初始化README、.gitignore或LICENSE
6. 点击 "Create repository"

### 2. 添加远程仓库并推送

在项目目录中执行以下命令：

```bash
# 进入项目目录
cd D:\Workbuddy\WorkBuddy\sql-mysql-course

# 重命名分支为main（GitHub标准）
git branch -M main

# 添加远程仓库（替换YOUR_USERNAME为你的GitHub用户名）
git remote add origin https://github.com/YOUR_USERNAME/sql-mysql-course.git

# 推送代码到GitHub
git push -u origin main
```

### 3. 配置GitHub Pages

1. 进入GitHub仓库页面
2. 点击 **Settings** → **Pages**
3. 在 **Build and deployment** 部分：
   - Source 选择：**GitHub Actions**
   - （不需要选择Branch，因为使用Actions）
4. 点击 **Save**

### 4. 等待GitHub Actions构建

1. 点击仓库的 **Actions** 标签
2. 等待 "Deploy to GitHub Pages" 工作流完成（通常需要2-5分钟）
3. 构建成功后，会显示绿色的✓

### 5. 访问网站

构建完成后，访问：
```
https://YOUR_USERNAME.github.io/sql-mysql-course/
```

**重要提示**：替换 `YOUR_USERNAME` 为你的实际GitHub用户名。

### 6. 更新配置文件

在推送代码之前，需要修改 `_config.yml` 文件中的URL配置：

```yaml
baseurl: "/sql-mysql-course"
url: "https://YOUR_USERNAME.github.io"  # 替换为你的GitHub用户名
```

## 项目结构

```
sql-mysql-course/
├── .github/
│   └── workflows/
│       └── pages.yml              # GitHub Actions工作流
├── _includes/                     # Jekyll模板（可选）
├── _layouts/                      # Jekyll布局（可选）
├── _posts/                        # 博客文章
│   └── 2026-03-19-welcome.md      # 欢迎文章
├── assets/                        # 静态资源（可选）
│   ├── css/                       # 样式文件
│   ├── js/                        # JavaScript文件
│   └── images/                    # 图片资源
├── 课程内容/
│   ├── 课程大纲.md
│   ├── SQL与MySQL课程讲义.md
│   ├── 案例计划.md
│   └── 习题集.md
├── 案例/                          # 案例代码（待添加）
├── _config.yml                    # Jekyll配置
├── index.md                       # 网站首页
├── README.md                      # 项目说明
└── DEPLOYMENT.md                  # 部署指南
```

## 故障排除

### 问题1：GitHub Actions构建失败

**解决方案**：
1. 检查 `_config.yml` 语法是否正确
2. 确保所有Markdown文件都有正确的front matter
3. 查看Actions构建日志，查看具体错误信息

### 问题2：网站无法访问

**解决方案**：
1. 确认GitHub Pages设置正确（Settings → Pages）
2. 确认GitHub Actions构建成功
3. 等待5-10分钟后再次访问
4. 检查URL是否正确

### 问题3：中文显示乱码

**解决方案**：
确保 `_config.yml` 中包含：
```yaml
encoding: "utf-8"
```

### 问题4：页面404

**解决方案**：
1. 检查 `baseurl` 配置是否正确
2. 确认仓库名称为 `sql-mysql-course`
3. 检查文件路径是否正确

## 下一步优化

部署成功后，可以考虑：

1. **添加自定义样式**：编辑 `assets/css/style.css`
2. **添加案例代码**：在 `案例/` 目录中添加各案例的SQL脚本
3. **添加图片**：在 `assets/images/` 中添加相关图片
4. **添加更多文章**：在 `_posts/` 中添加更多学习笔记
5. **配置域名**：在GitHub Pages设置中绑定自定义域名

## 技术支持

如有问题，请：
1. 查看GitHub Actions构建日志
2. 参考Jekyll官方文档：https://jekyllrb.com/docs/
3. 查看GitHub Pages文档：https://docs.github.com/en/pages

---

**部署指南版本**：v1.0
**创建日期**：2026年3月19日
