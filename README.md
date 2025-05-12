# Git版本控制工具学习笔记

## 一、学习资料来源
1. [Git官方文档](https://git-scm.com/book/zh/v2)（推荐Pro Git中文版）
2. [廖雪峰Git教程](https://www.liaoxuefeng.com/wiki/896043488029600)
3. [GitHub官方指南](https://docs.github.com/zh)


---

## 二、实践流程记录

### 1. 本地环境搭建
#### 安装Git
- Windows：官网下载安装包，勾选`Add to PATH`选项
- Mac：`brew install git` 或使用Xcode Command Line Tools
- Linux：`sudo apt-get install git`（Debian系）

#### 配置基础信息
```bash
git config --global user.name "YourName"
git config --global user.email "your@email.com"
git config --global core.editor code  # 设置VS Code为默认编辑器
```

### 2. 本地仓库操作
```bash
mkdir myproject && cd myproject
git init
echo "# My Project" > README.md
git add .
git commit -m "Initial commit"
```

### 3. 远程仓库配置
#### 平台选择
- 注册GitHub（国际平台）
- 注册Gitee（国内镜像）

#### SSH密钥配置
```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
cat ~/.ssh/id_ed25519.pub  # 复制到平台SSH Keys设置
```

#### 远程仓库操作
```bash
git remote add origin git@github.com:username/repo.git
git push -u origin main
```

### 4. 提交代码实践
1. 首次提交：创建README.md
2. 二次提交：添加.gitignore文件
3. 三次提交：实现基础功能模块
```bash
# 典型提交过程
git status
git diff
git add changed_file.txt
git commit -m "feat: add file validation"
git push
```

---

## 三、遇到的典型问题及解决方案

### 问题1：SSH连接失败
- **现象**：`Permission denied (publickey)`
- **解决**：
  1. 检查`~/.ssh`目录权限设置为700
  2. 使用`ssh -T git@github.com`测试连接
  3. 重新生成密钥并更新平台配置


### 问题3：误提交大文件
- **处理方案**：
  1. 使用`git filter-branch`清除历史记录
  2. 或使用BFG Repo-Cleaner工具
  3. 添加`.gitignore`预防问题

---

## 四、学习心得与建议

### 核心收获
1. 掌握了分布式版本控制的核心思想
2. 熟练使用分支管理策略（Git Flow）
3. 理解工作区/暂存区/版本库的关系
4. 体验了CI/CD的集成应用

### 推荐学习路线
1. 基础命令 → 分支管理 → 协作流程 → 高级技巧
2. 配套学习Markdown语法
3. 结合IDE（VSCode/IDEA）的Git工具使用

