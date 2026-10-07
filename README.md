# Scientific Graphical Abstract

基于论文证据设计、审核和修订科研图形摘要的 Codex skill。重点是核心发现、科学关系与文字准确性；支持提示词准备和已有图片审核。

A Codex skill for evidence-grounded scientific graphical abstracts: identify the central finding, plan the composition, prepare image prompts, inspect actual images, and revise scientific or textual errors.

## 安装 / Installation

下载源码或解压技能 ZIP，将整个 `scientific-graphical-abstract` 文件夹复制到 Codex 的 skills 目录：设置了 `CODEX_HOME` 时使用其下的 `skills/`，否则使用 `~/.codex/skills/`。

确保最终路径为 `skills/scientific-graphical-abstract/SKILL.md`，不要多嵌套一层同名目录。重新启动 Codex 会话后调用技能。本包无需 Python、额外脚本或专用绘图工具即可阅读和使用；实际论文读取、绘图及导出能力取决于运行环境。

Download the source or extract the ZIP, then copy the whole skill folder into `CODEX_HOME/skills/` if configured, otherwise `~/.codex/skills/`. Ensure `SKILL.md` is directly inside the skill folder. Start a new Codex session and invoke the skill. Reading the instructions requires no extra runtime; document access, image generation, and editing depend on the host environment.

## 调用示例 / Examples

**新建摘要图 / New abstract**

```text
使用 $scientific-graphical-abstract，根据我上传的论文及补充材料，
先提炼核心发现和证据表，再给出 graphical abstract 布局和英文提示词。
这一步只需要设计方案。
```

**审核已有图片 / Review an image**

```text
Use $scientific-graphical-abstract to review the attached graphical
abstract against the attached paper. Identify scientific, labeling,
and arrow-direction errors with source locations. Do not edit yet.
```

**证据不足 / Incomplete evidence**

```text
使用 $scientific-graphical-abstract。我只有论文标题和一段 AI 解读，
请先确认论文和可核实的结论，列出缺失资料，不把解读直接当作事实。
```

## 输入与交付 / Inputs and outputs

提供论文全文或可靠链接、必要补充材料；审核时提供实际图片。可选输入包括期刊要求、参考布局、指定绘图工具和输出格式。仅有摘要时，结论范围受其内容限制。

按任务交付核心发现、证据表、布局、精确标签、英文提示词、问题清单或修订图文件。不会默认生成所有格式或额外调用绘图服务。

Provide a paper or reliable link and relevant supplementary materials. Image review requires the actual image. Optional inputs include journal specifications, layout references, a preferred image tool, and output format. Deliverables are selected for the request: finding, evidence table, layout, label list, prompts, review report, or revised image.

## 工作方式与限制 / Approach and limitations

先核验证据，再锁定图中内容，最后审核实际图片。已有图片可以直接进入审核流程。复杂标签或反复错字时采用无文字素材加可编辑文字和箭头。

AI 对话不等于科学证据；不会凭空补全数据、机制或临床建议。图像生成不是科学验证，位图也不是可编辑矢量图。无法访问原文或看清图片时会说明检查范围，保留待核验项，不保证投稿通过。用户指定工具不可用时交付提示词，不声称已经调用。

Verify the evidence, lock the content, then inspect the actual image. Use text-free assets with editable labels and arrows when generated text is unreliable. AI conversations are not primary evidence. The skill does not fabricate measurements, mechanisms, or clinical recommendations, guarantee journal acceptance, or claim unavailable tool access.

## 文件 / Files

- `SKILL.md`：入口与任务流程 / Entry point and workflow.
- `references/quality-checklist.md`：实图审核 / Image review checklist.
- `references/prompt-template.md`：生成及修订模板 / Prompt and revision templates.
- `agents/openai.yaml`：界面元数据 / Interface metadata.

## 许可 / License

本仓库的技能文本与模板采用 [MIT License](LICENSE)。第三方论文、参考图片、素材和外部服务不因本许可证获得再分发或商业使用授权；使用这些资源时遵守各自的授权条件。

The skill instructions and templates are licensed under MIT. This license does not grant rights to third-party papers, figures, assets, or services. No private conversation transcript or third-party scientific figure is bundled.
