# CryptoPulse 白皮书 i18n 国际化 — 集成说明

## 概述

白皮书页面已更新为支持 vue-i18n 国际化。所有文本内容通过 `$t('whitepaper.xxx')` 调用，
切换语言时白皮书内容会自动切换为对应语言。

## 文件说明

| 文件 | 说明 |
|------|------|
| `WhitepaperPage.vue` | 更新后的 Vue 组件（所有文本改用 `$t()` 调用） |
| `whitepaper.en.js` | 英文翻译键值对 |
| `whitepaper.zh.js` | 中文翻译键值对 |

## 集成步骤

### 1. 替换 WhitepaperPage.vue

用新的 `WhitepaperPage.vue` 替换原来的文件（保持路径不变）。

### 2. 合并翻译文件到现有 i18n 配置

在你们项目的 i18n 配置文件中，将翻译内容合并到对应的 locale messages 中：

```js
// 导入白皮书翻译
import whitepaperEn from './whitepaper.en.js'
import whitepaperZh from './whitepaper.zh.js'

// 合并到现有的 messages 对象中
const messages = {
  en: {
    // ... 现有的英文翻译
    whitepaper: whitepaperEn,
  },
  zh: {
    // ... 现有的中文翻译
    whitepaper: whitepaperZh,
  }
}
```

或者，如果你们的 i18n messages 已经是一个大对象（例如打包在 JS bundle 中），
可以在初始化时通过 `mergeLocaleMessage` 动态合并：

```js
import whitepaperEn from './whitepaper.en.js'
import whitepaperZh from './whitepaper.zh.js'

i18n.mergeLocaleMessage('en', { whitepaper: whitepaperEn })
i18n.mergeLocaleMessage('zh', { whitepaper: whitepaperZh })
```

### 3. 验证

- [ ] 切换到英文，白皮书内容显示英文
- [ ] 切换到中文，白皮书内容显示中文
- [ ] 目录（Table of Contents）文本随语言切换
- [ ] 表格标题和内容随语言切换
- [ ] 3 张图片的 alt 文本随语言切换（查看源代码确认）
- [ ] 手机端响应式布局正常

## 注意事项

1. **HTML 格式化** — 部分文本包含 `{bold}` / `{boldEnd}` 等占位符，组件内通过 `v-html` + 参数替换为 `<strong>` 标签。这是正常的 vue-i18n 插值用法。
2. **图片不需要翻译** — 3 张架构图是通用的，仅 alt 文本和 figcaption 随语言切换。
3. **数字不翻译** — 代币数量（350M、200M 等）和百分比（35%、20% 等）在中英文中保持一致。
4. **中文翻译为 AI 生成** — 建议校对后再正式上线。
