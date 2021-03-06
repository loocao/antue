---
category: Components
cols: 1
type: Navigation
title: Menu
subtitle: 导航菜单
---

为页面和功能提供导航的菜单列表。

## 何时使用

导航菜单是一个网站的灵魂，用户依赖导航在各个页面中进行跳转。一般分为顶部导航和侧边导航，顶部导航提供全局性的类目和功能，侧边导航提供多级结构来收纳和排列网站架构。

更多布局和导航的使用可以参考：[通用布局](/components/layout)。

## API

```html
<atu-menu>
  <menu-item>菜单项</menu-item>
  <sub-menu title="子菜单">
    <menu-item>子菜单项</menu-item>
  </sub-menu>
</atu-menu>
```

### Menu

| 参数     | 说明           | 类型     | 默认值       |
|----------|---------------|----------|--------------|
| theme    | 主题颜色 | string: `light` `dark` | `light` |
| mode | 菜单类型，现在支持垂直、水平、和内嵌模式三种 | string: `vertical` `horizontal` `inline` | `vertical` |
| selectedKeys | 当前选中的菜单项 key 数组 | string[] |      |
| defaultSelectedKeys | 初始选中的菜单项 key 数组 | string[] |      |
| openKeys | 当前展开的 SubMenu 菜单项 key 数组 | string[] |  |
| defaultOpenKeys | 初始展开的 SubMenu 菜单项 key 数组 |  |      |
| inlineIndent | inline 模式的菜单缩进宽度 | number | 24 |
| multiple | 是否允许多选 | boolean | false |
| inlineCollapsed | inline 时菜单是否收起状态 | boolean | - |
| selectable | 是否允许选中 | boolean | true |

### Events 

| 参数     | 说明           | 类型     | 默认值       |
|----------|---------------|----------|--------------|
| open-change | SubMenu 展开/关闭的回调 | function(openKeys: string[]) | noop |
| select | 被选中时调用 | function({ e, vm, path, index }) | 无   |
| de-select | 取消选中时调用，仅在 multiple 生效 | function({ e, vm, path, index }) | - |
| click | 点击 MenuItem 调用此函数  | function({ e, vm, path, index }) | - |


### Menu.Item

| 参数     | 说明           | 类型     | 默认值       |
|----------|----------------|----------|--------------|
| disabled    | 是否禁用 | boolean   |  false  |
| index   | item 的唯一标志 |  string |  |

### Menu.SubMenu

| 参数     | 说明           | 类型     | 默认值       |
|----------|----------------|----------|--------------|
| disabled    | 是否禁用 | boolean   |  false  |
| index | 唯一标志 |  string |  |
| title    | 子菜单项值 | string |    |

### Menu.SubMenu Slots

| 参数     | 说明           | 类型     | 默认值       |
|----------|----------------|----------|--------------|
| title    | 子菜单项值 | string | DOM  |

### Menu.ItemGroup

| 参数     | 说明           | 类型     | 默认值       |
|----------|----------------|----------|--------------|
| title    | 分组标题       | string\|ReactNode |    |

