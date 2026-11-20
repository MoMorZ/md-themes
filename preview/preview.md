# 主题视觉与全语法预览样本 (Theme Preview)

这是一份用于检验 Markdown 主题配色、对比度与排版细节的标准样本文档，覆盖了中英文混排及常见语法元素，可用于日常调色验收与主题截图展示。

---

## 1. 标题层级展示 (Headings)

# 一级标题 H1 · 自然柔和的阅读体验
## 二级标题 H2 · 环境光与对比度平衡
### 三级标题 H3 · 含 `inline code` 与 [链接样式](https://example.com)
#### 四级标题 H4 · 低饱和度色彩层次
##### 五级标题 H5 · 次级小节标题
###### 六级标题 H6 · 辅助说明层级

---

## 2. 正文与行内修饰 (Inline Typography)

长时间注视屏幕时，**过高的纯白/纯黑反差**容易引起视觉眩光或视网膜残影，而 *适度收敛明度与饱和度* 的暖纸色与森林灰底色能显著减轻眼部调节负担。

常见行内语法组合测试：
- **加粗重点文字**、*斜体强调文字*、***粗斜体混合***、~~已废弃的删除线内容~~
- 行内代码如 `surface.canvas` 与 `const mode = 'everforest'`，以及快捷键提示 <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>P</kbd>
- 重点标记测试：==这是一段使用双等号标记的高亮文本==，以及高亮内嵌代码 ==请检查 `accent.background` 配置项==
- 外部超链接：[Everforest 官方调色板参考](https://github.com/sainnhe/everforest) 与脚注引用示例[^1]

---

## 3. 引用块与多层嵌套 (Blockquotes)

> **单层引用提示**：好的护眼主题应当像自然光下翻开的纸质书页——既不刺眼发光，也不灰暗费力。
>
> > **二级嵌套引用**：测试多层嵌套时的左侧竖线颜色与背景层次，包含 `行内代码` 与 **加粗文本**。
> >
> > > **三级嵌套引用**：极端嵌套层级下的文字可读性与边距对齐检验。

---

## 4. 列表与任务清单 (Lists & Task Lists)

### 无序与有序列表
- **浅色模式（Light）**：适合白天或明亮室内环境
  - 暖米色 / 燕麦绿底色（如 `#f3ead3`）
  - 深石板灰正文（如 `#5c6a72`）
- **深色模式（Dark）**：适合夜间开灯或偏暗环境
  1. 主画布采用柔和森林深灰（`#2d353b`）
  2. 侧边栏与面板略深一级（`#232a2e`）以区分层次
  3. 正文采用温暖米灰（`#d3c6aa`）替代刺眼纯白

### 任务状态测试（含父子嵌套）
- [x] 已完成任务：建立 `md-themes` 仓库目录结构
- [x] 已完成父任务（子项未全部完成）：适配 MarkFlowy 双模式主题
  - [x] 完成浅色与深色基础表面及文字 Token 映射
  - [ ] 待观察：长文档滚动与弹窗悬浮菜单细节体验
- [ ] 未完成任务：后续按需扩展 Typora 与 Obsidian 样式

---

## 5. 代码块与语法高亮 (Code Blocks)

```typescript
// TypeScript 语法高亮测试：注释、关键字、函数、字符串、数字与类型
interface PaletteConfig {
  id: string;
  mode: 'light' | 'dark';
  contrastRatio: number;
}

export function resolveEyeCareTheme(ambientLux: number): PaletteConfig {
  const isDaylight = ambientLux >= 250;
  return {
    id: 'everforest',
    mode: isDaylight ? 'light' : 'dark',
    contrastRatio: isDaylight ? 6.8 : 7.4,
  };
}
```

```python
# Python 语法高亮测试
def check_luminance(hex_color: str, threshold: float = 0.85) -> bool:
    """检查背景亮度是否处于舒适区间"""
    rgb = [int(hex_color[i:i+2], 16) / 255.0 for i in (1, 3, 5)]
    luminance = 0.2126 * rgb[0] + 0.7152 * rgb[1] + 0.0722 * rgb[2]
    return luminance <= threshold
```

---

## 6. 数据表格 (Tables)

| 主题变体 | 适用光线 | 主背景色 | 侧栏面板 | 正文颜色 | 强调主色 |
| :--- | :---: | :---: | :---: | :---: | ---: |
| **Everforest Light** | 白天 / 明亮室内 | `#f3ead3` | `#eae4ca` | `#5c6a72` | ==森林鼠尾草绿== |
| **Everforest Dark** | 夜晚 / 柔和暗光 | `#2d353b` | `#232a2e` | `#d3c6aa` | ==柔和嫩芽绿== |
| 默认纯白对照 | 强光下易眩光 | `#ffffff` | `#f9fafb` | `#000000` | 高饱和亮蓝 |

---

## 7. 数学公式 (Math Equations)

行内公式渲染测试：视觉对比度通常采用相对亮度公式 $C = (L_1 + 0.05) / (L_2 + 0.05)$ 计算，其中 $L_1 > L_2$。

块级公式渲染测试（检验深浅色模式下的公式符号颜色是否清晰）：

$$
\mathcal{L}_{\text{comfort}}(\theta) = \sum_{i=1}^{N} w_i \cdot \left\| \Delta E_{00}\big(c_i(\theta), c_i^*\big) \right\|_2^2 + \lambda \cdot \text{Glare}(L_{\text{bg}})
$$

---

[^1]: 脚注样式测试：验证底部辅助小字、返回箭头与分割线在浅色/深色背景下的可读性。
