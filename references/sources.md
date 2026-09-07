# 来源与改造说明

2026-09-07：依据用户提供的三类失败链路及已确认设计原则重新编写。选择性借鉴以下公开技能的判断方法，未复制其脚本、自动化或完整工作流。链接指向可变化的上游 main，后续更新需重新核对。

- Superpowers systematic-debugging：假设和最小实验；不采用失败次数直接判定架构问题的规则。
  https://github.com/obra/superpowers/blob/main/skills/systematic-debugging/SKILL.md
- workers.io WIO：保留故障机制的最窄测试与测试价值判断；不引入完整测试平台或强制多代理流程。
  https://github.com/workersio/skills/blob/main/plugins/wio/skills/wio/SKILL.md
- chemny self-improving-skills：经验分类、路由、验证后提升；不引入后台扫描和看板。
  https://github.com/chemny/self-improving-skills/blob/main/SKILL.md
- AnimaApp smarter-agent：以行为反例验证规则变化；改为按风险触发、有限审查。
  https://github.com/AnimaApp/smarter-agent/blob/main/skills/smarter-agent/SKILL.md

上述四个仓库核验时均采用 MIT。为保留改编来源的许可信息，一并保留以下版权与完整许可。CodeScene 仅作为调研背景，不包含其文本或软件。

Copyright (c) 2025 Jesse Vincent
Copyright (c) 2026 workers.io
Copyright (c) 2026 merlin chen
Copyright (c) 2026 Ofer LaOr

MIT License

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
