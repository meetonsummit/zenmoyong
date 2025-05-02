# GitHub 使用指南

## Git 是什么

Git 是一个分布式版本控制系统，用于跟踪文件的变化，特别是在软件开发过程中协调多人共同开发的工作。它可以记录每一次代码的修改历史，方便回溯和协作。

## GitHub 是什么

GitHub 是基于 Git 的代码托管平台，是最流行的远程代码仓库服务之一。它提供了代码存储、版本控制、问题跟踪、协作开发等功能。

## 基本概念

- **仓库(Repository)**: 存储项目代码的地方，包含所有文件和修改历史
- **Fork**: 复制他人的仓库到自己账号下，创建一个独立的副本
- **Clone**: 将远程仓库下载到本地
- **Commit**: 提交对代码的修改
- **Push**: 将本地修改推送到远程仓库
- **Pull**: 从远程仓库获取最新代码

## 如何使用 GitHub

### 1. 创建账号

访问 [GitHub](https://github.com) 注册账号。

### 2. 设置个人访问令牌(PAT)

由于 GitHub 不再支持直接使用账号密码认证，需要设置 PAT：

1. 点击右上角头像
2. 选择 Settings
3. 左侧菜单选择 Developer settings
4. 选择 Personal access tokens
5. 点击 "Generate new token (classic)"
6. 设置令牌名称和过期时间（建议设置较长时间）
7. 选择需要的权限（至少需要 repo 权限）
8. 点击生成并保存令牌（只显示一次，请妥善保存）

### 3. 连接远程仓库

```bash
# 初始化本地仓库
git init

# 连接远程仓库（这就是你的"钥匙"）
git remote add origin https://github.com/用户名/仓库名.git
```

### 4. 克隆仓库到本地

```bash
git clone https://github.com/用户名/仓库名.git
```

当系统弹出认证窗口时：
- 用户名输入你的 GitHub 用户名
- 密码输入你的 PAT（不是账号密码）

### 5. 提交代码

```bash
# 添加修改的文件
git add .

# 提交修改
git commit -m "提交说明"

# 推送到远程仓库
git push origin main
```

### 6. Fork 他人仓库

1. 访问想要 Fork 的仓库页面
2. 点击右上角的 "Fork" 按钮
3. 选择要 Fork 到的账号

### 7. 更新 Fork 的仓库

```bash
# 添加原始仓库为上游仓库
git remote add upstream https://github.com/原作者/原仓库.git

# 获取原仓库的最新代码
git fetch upstream

# 合并到本地分支
git merge upstream/main
```

## 注意事项

1. **国内连接问题**：
   - 上传代码时不要开 VPN
   - 可以直接使用手机热点推送代码

2. **认证问题**：
   - GitHub 已不支持账号密码认证，必须使用 PAT
   - 如果认证出错，打开 Windows 凭据管理器删除相关凭据:
     - 控制面板 → 用户账户 → 凭据管理器 → Windows 凭据
     - 找到 github.com 相关条目并删除

3. **SSH 配置**：
   - 初学者可以先使用 HTTPS+PAT 方式，不必急于配置 SSH

4. **Fork 仓库注意**：
   - Fork 的仓库只是原仓库的快照，不会自动同步更新
   - 需要定期手动同步原仓库的更新

通过以上步骤，你就可以开始使用 GitHub 进行代码管理和协作开发了。
