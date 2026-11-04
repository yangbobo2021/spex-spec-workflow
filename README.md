# spex-spec-workflow

用于管理软件项目 SPEC 的 Codex Skill：初始化、从代码补齐规格、功能变更、质量审查，以及 Spex 标准升级和旧目录迁移。

## 安装与调用

将本仓库克隆到个人技能目录；目标目录已有内容时先检查，避免覆盖。

```sh
git clone https://github.com/yangbobo2021/spex-spec-workflow.git ~/.codex/skills/spex-spec-workflow
```

在 Codex 中调用：

```text
$spex-spec-workflow 为当前项目初始化 SPEC。
$spex-spec-workflow 根据现有代码补充 SPEC，并标明证据与待确认事项。
$spex-spec-workflow 检查本次修改与 SPEC 是否一致。
```

完整规则见 [SKILL.md](SKILL.md)，维护验收见 [acceptance-cases.md](references/acceptance-cases.md)。

从“只有宿主、尚未安装 Skill”开始的公开[手动交付验收步骤](https://github.com/yangbobo2021/skills-acceptance-demo/blob/manual-v1.0.0/MANUAL-ACCEPTANCE.md)包含 Codex/Claude Code 安装、独立目录初始化 SPEC，以及 SubLang 四工作流的人工验收。

## 版本维护

本仓库是 Skill 的 Git 工作副本。日常维护直接修改、检查差异并提交，不创建备份版本文件夹。

```sh
git status
git diff
git add SKILL.md agents references
git commit -m "Describe the skill change"
git push
```

从远端更新使用 `git pull --ff-only`；回退已发布改动优先使用 `git revert`。保留用户未提交内容，不自动 stash 或重置工作区。

## 已有验证

2026-11-04 的历史验收包括临时项目检查、Linux ARM64 Docker 环境和独立 Codex 会话，以及许可证不阻塞、缺工具、脏工作区升级等定向回归。测试方法和边界见验收参考；这些结果不构成所有平台和模型的通用保证。
