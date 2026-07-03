# Offline Sales Skills

这个仓库收集面向线下门店销售场景的 Codex Skills。当前包含一个联想门店销售话术 skill：输入产品照片、链接或文字描述，输出简短产品亮点和可直接口播的销售话术。

## 当前 Skill

### `lenovo-store-sales`

适用于联想门店销售赋能，覆盖 ThinkPad、Yoga、拯救者、小新、台式机、一体机、平板、显示器、配件等常见产品。

它可以处理：

- 产品照片：识别可见型号、系列、配置标签、外观和价格牌信息。
- 产品链接：读取用户提供的链接，并在需要时核验官方或可信公开信息。
- 文字描述：从产品名、配置、客群、预算和顾虑中提炼卖点。

默认输出：

- `产品亮点短介绍`：约 80-120 字，适合门店直接口播。
- `销售话术`：3-5 条，覆盖开场、需求匹配、体验引导、对比促单和异议处理。
- `核验/注意`：简短说明事实依据或关键不确定信息，避免编造参数、价格、库存或保修政策。

如果产品型号或配置不清楚，skill 会先追问，不会直接生成具体产品卖点。例如只说“小新笔记本”“ThinkPad”或照片里只看到品牌标识时，它会要求补充完整型号、配置标签、产品链接或更清晰照片。

## 安装到 Codex

克隆仓库后，把 skill 目录复制到本机 Codex skills 目录：

```bash
git clone git@github.com:wyuzhi/offline-sales.git
mkdir -p ~/.codex/skills
cp -R offline-sales/lenovo-store-sales ~/.codex/skills/
```

然后新开一个 Codex 对话即可调用：

```text
Use $lenovo-store-sales to turn this Lenovo product photo into concise retail highlights and sales talk tracks.
```

也可以中文调用：

```text
用 $lenovo-store-sales，根据这张联想产品照片生成一段产品亮点和 3-5 条门店销售话术。
```

## 使用示例

文字输入：

```text
用 $lenovo-store-sales：
产品标签显示：[完整型号/年份]，[处理器]，[内存]，[硬盘]，[屏幕]。主要卖给大学生和轻办公用户，客户担心性能不够、价格有点高。
```

链接输入：

```text
用 $lenovo-store-sales：
请根据这个产品链接生成门店销售话术，并和同价位竞品做公平对比。
```

照片输入：

```text
用 $lenovo-store-sales：
这是一张门店展机照片，请根据能看清的信息生成销售话术。看不清的参数不要编造。
```

模糊输入会被追问：

```text
用 $lenovo-store-sales：
小新笔记本，适合大学生，帮我写话术。
```

预期行为：不会直接生成完整销售话术，而是先询问具体型号、配置或产品链接。

## 给其他 Agent 使用

非 Codex agent 通常不能自动识别 `$lenovo-store-sales`，但仍然可以使用这个 skill 的内容：

1. 把 `lenovo-store-sales/SKILL.md` 作为主提示或系统说明。
2. 把 `lenovo-store-sales/references/sales-framework.md` 作为参考知识。
3. 要求 agent 按 README 或 SKILL.md 的默认格式输出。

## 注意事项

- 不内置静态产品参数库；涉及最新配置、价格、促销、库存、保修等信息时，应以当前官方或可信来源为准。
- 不承诺价格、库存、赠品、售后政策或性能表现，除非用户明确提供或已完成核验。
- 竞品对比应保持公平，只比较同品类、相近价位或相近使用场景的产品。
