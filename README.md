# GitHubStarMover

**GitHubStarMover** 是一款用于将一个 GitHub 账户中的 Star 仓库迁移到另一个 GitHub 账户的 Python 工具。通过使用 GitHub API，该工具能够自动化地将源账户的所有 Star 仓库同步到目标账户，无需手动操作，简化了迁移过程。

## 功能

- 获取源账户的 Star 仓库列表。
- 将源账户的 Star 仓库同步到目标账户。
- 支持分页加载多个 Star 仓库。

## 环境要求

- Python 3.x
- `requests` 库：可以通过 `pip install requests` 安装。

## 安装和使用

### 1. 克隆仓库

首先，克隆该项目到本地：

```bash
git clone https://github.com/CrazyCodingConclave/GitHubStarMover.git
cd GitHubStarMover
```
### 2. 安装依赖

安装项目所需的依赖：

```bash
pip install requests
```

### 3. 配置 GitHub 令牌

你需要为源账户和目标账户创建 GitHub Personal Access Token，并确保令牌具有 `repo` 和 `user` 权限。

在 `GitHubStarMover.py` 文件中，编辑以下配置：

```python
source_token = 'YOUR_SOURCE_TOKEN'  # 源账户的 GitHub 令牌
source_username = 'YOUR_SOURCE_USERNAME'  # 源账户的用户名
target_token = 'YOUR_TARGET_TOKEN'  # 目标账户的 GitHub 令牌
```

### 4. 运行脚本

运行脚本将源账户的 Star 仓库同步到目标账户：

```bash
python GitHubStarMover.py
```

该脚本会列出源账户的所有 Star 仓库，并在目标账户中重新 Star 这些仓库。

### 5. 完成

迁移完成后，你将在目标账户的 Star 列表中看到与源账户相同的仓库。

## 注意事项

- 请确保为两个 GitHub 账户生成的 Personal Access Token 都具有足够的权限，特别是需要对仓库进行 Star 的权限。
- 如果有大量仓库，可能会多次请求 GitHub API，建议留意 API 请求限制。
