# Intent Narrator

Google Antigravity 全局规则插件：在执行多步任务（排查、修改、验证）时输出**分层意图微播报**，让 AI 的思考假设、定位结论与改动边界实时可见，方便用户随时跟进与纠偏。

## 核心规则摘要

- **只报意图与判断，不复读工具名**：每轮动作前输出 1 句单行中文（约 15~40 字），禁止「正在读取 xxx」等空洞流水账。
- **探索期允许并行**：同类只读操作可并行，切换排查方向前必播报 1 句简报。
- **动手前必报方案边界**：写文件、改配置或执行有副作用命令前，先交代「定位结论 + 准备改哪里/不改哪里」。
- **简单任务豁免**：纯对话问答直接回复，不强行播报。

完整规则见 [rules/AGENTS.md](./rules/AGENTS.md)。

## 安装方式

将仓库克隆到 Antigravity 全局插件目录即可自动生效：

```bash
git clone https://github.com/UsonTong/intent-narrator.git ~/.gemini/config/plugins/intent-narrator
```

校验插件加载状态：

```bash
agy plugin validate ~/.gemini/config/plugins/intent-narrator --strict
agy plugin list
```

## 常用开关命令

- 临时关闭：`agy plugin disable intent-narrator`
- 重新启用：`agy plugin enable intent-narrator`
