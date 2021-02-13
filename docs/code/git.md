# Git
> Git 是一个开源的分布式版本控制系统，可以有效、高速地处理从很小到非常大的项目版本管理。

## 配置 Git 全局用户名

```bash
git config --global user.name "Your Name Here"
git config --global user.email "your_email@youremail.com"
```

## 配置 Git 仓库用户名

```bash
git config user.name "Your Name Here"
git config user.email "your_email@youremail.com"
```

## Git Ignore
> 创建一个新文件 ~/.gitignore ，并将以下内容添加进去，这样全部 git 仓库将会忽略以下内容所提及的文件。

```bash
vim ~/.gitignore
```

```vim
# Folder view configuration files
.DS_Store
Desktop.ini

# Thumbnail cache files
._*
Thumbs.db

# Files that might appear on external disks
.Spotlight-V100
.Trashes

# Compiled Python files
*.pyc

# Compiled C++ files
*.out

# Application specific files
venv
node_modules
.sass-cache

# Temp File
*.swp
*.swa
*.swo

# github merge file
*.orig

#vscode 
.vscode
```