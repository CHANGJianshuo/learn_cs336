# 如何用 uv 管理 Python 环境

## Prompt

> 教我如何用uv管理环境

## AI 回答

### 基本概念

```
uv 管理的东西：
├── Python 版本        # 可以装多个版本共存
├── 虚拟环境 (.venv)   # 每个项目一个，互相隔离
├── 依赖 (pyproject.toml + uv.lock)  # 声明 + 锁定
```

### Python 版本管理

```bash
uv python list               # 查看可用的 Python 版本
uv python install 3.12       # 安装新版本
uv python pin 3.11           # 当前项目锁定用 3.11
```

### 虚拟环境

```bash
uv venv                      # 创建 .venv（用 .python-version 指定的版本）
uv venv --python 3.12        # 指定版本创建
source .venv/bin/activate     # 激活
deactivate                    # 退出
```

### 依赖管理（最常用）

```bash
uv add torch                  # 添加依赖（自动装 + 写入 pyproject.toml）
uv add "numpy>=1.24,<2.0"    # 指定版本范围
uv add jupyterlab pandas matplotlib  # 一次装多个
uv remove pandas              # 移除依赖
uv sync                       # 按 uv.lock 还原环境（换电脑/云机器时用）
```

### 运行命令（推荐，不需要手动 activate）

```bash
uv run python train.py        # 自动用 .venv 里的 python 运行
uv run jupyter lab            # 自动用 .venv 里的 jupyter
uv run pytest                 # 跑测试
```

### 实际工作流

```bash
# 日常开发
cd ~/learn_cs336
uv run jupyter lab            # 开 JupyterLab

# 需要新包
uv add wandb                  # 装 wandb
uv add transformers datasets  # 装 HuggingFace 全家桶

# 云机器上复现环境
git clone <your-repo>
cd learn_cs336
uv sync                       # 一键还原所有依赖，完全一致
```

### 对比 pip 全局安装

| 以前 (pip 全局) | 现在 (uv) |
|-----------------|-----------|
| `pip install torch` | `uv add torch` |
| 装到全局，影响所有项目 | 只装到当前项目的 .venv |
| 没有锁文件，版本不确定 | `uv.lock` 锁定精确版本 |
| 换机器靠 `pip freeze > requirements.txt` | `uv sync` 一键还原 |
| 删包不知道删哪些 | `uv remove` 自动清理依赖树 |

### 核心三个命令

```bash
uv add <包名>       # 装包
uv remove <包名>    # 删包
uv run <命令>       # 运行
```
