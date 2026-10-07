# 提示词与修订模板

下面的变量是使用时填写的模板字段，不是可直接提交的最终提示词。根据实际需求删除无关字段；填入内容必须来自证据表和标签清单。

## 科学内容锁定

在写英文提示词前，先明确：核心发现；模型与条件；允许出现的节点和关系；精确标签；禁止新增的内容；布局；交付格式。未核验的关系不能进入最终图。

## 英文整图草稿提示词

```text
Create a scientific graphical abstract illustrating this verified finding:
{{core_finding}}

Study context and evidence boundaries:
{{model_conditions_and_limits}}

Layout and reading order:
{{panel_layout_and_visual_hierarchy}}

Depict only these objects and relationships:
{{approved_objects_edges_and_locations}}
Use arrows for activation or progression and T-bars for inhibition only
where specified. Explain any hypothesis edges with a distinct legend.

Use exactly these labels, with the stated spelling and capitalization:
{{exact_label_list}}

Visual style and output requirements:
{{style_dimensions_and_format}}
Keep the central finding visually prominent and the composition legible.

Do not add:
{{task_specific_exclusions}}
Do not invent pathway nodes, chemical structures, measurements,
statistical marks, clinical recommendations, logos, or signatures.
```

提示词要求不保证生成结果正确。生成后必须审核实图；不要把模型生成的“vector style”当作真实矢量文件。

## 无文字素材提示词

```text
Create a clean scientific illustration asset of {{approved_object}}.
Show {{verified_morphology_location_and_state}}.
Use {{visual_style_and_palette}} with {{background_requirement}}.
Leave clear space for labels to be added separately.
Do not include text, letters, numbers, arrows, molecular formulas,
logos, signatures, or additional biological structures.
```

分别生成必要素材，再在可编辑图面中添加核验的标签与连线。透明背景仅在用户或拼版要求需要时设置。即使素材无文字，也要检查结构和形态准确性。

## 局部修订提示词

```text
Edit the supplied image only in {{target_region}}.
Replace {{observed_incorrect_element}} with {{verified_replacement}}.
Correct these relationships: {{edge_corrections}}.
Use these exact labels: {{corrected_labels}}.
Preserve {{user_required_elements_and_verified_surroundings}}.
Do not add new scientific content or change unrelated regions.
```

只有实际编辑工具可引用到目标图片时使用此模板；不要将文字描述当成已经提供图片。修订后核对目标区域和相邻关系是否变化。

## 审核报告

```text
审核依据：论文身份、可读资料范围、实际图片版本。
核心发现：一句话。
问题清单：位置 | 实际内容 | 问题与影响 | 依据 | 修正。
待核验项：缺少什么资料，影响哪些结论。
修改顺序：机制/数据 → 标签/符号 → 可读性。
复核结果：已解决的问题、仍然存在的问题、实际交付格式。
```
