# JupyterLab 是什么 & 如何使用

## Prompt

> jupyterlab装好了吗 如何使用

## AI 回答

JupyterLab 已经通过 `uv add jupyterlab` 装在项目的 `.venv` 虚拟环境里。

### 启动方式

```bash
cd ~/learn_cs336
source .venv/bin/activate
jupyter lab
```

或者用 uv 直接运行（不需要手动 activate）：

```bash
cd ~/learn_cs336
uv run jupyter lab
```

启动后终端会显示一个 `http://localhost:8888/lab?token=xxx` 的链接，在 Windows 浏览器里打开即可。

### JupyterLab 是什么

- Jupyter Notebook 的升级版，浏览器里的交互式编码环境
- 一个 cell 写几行代码，按 Shift+Enter 立即执行看结果
- 特别适合边学边跑：写一段、跑一段、看输出、画图
- CS336 的课程材料本身就有大量 `.ipynb` 文件

### 两种打开 .ipynb 的方式

| 方式 | 说明 |
|------|------|
| VS Code 内置 | VS Code 自带 Jupyter 插件，直接打开 .ipynb |
| JupyterLab | 独立的浏览器界面，功能更完整 |
