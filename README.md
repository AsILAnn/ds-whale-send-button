# ds-whale-send-button 🐋

把 DeepSeek Harness Web 对话输入栏的**主发送按钮图标**替换为 **DeepSeek 官方鲸鱼 logo**。

- 不改发送行为，只换图标外观
- CSS `mask` 叠加官方鲸鱼图形，颜色跟随按钮文字色（`currentColor`），**亮色/暗色主题自适应**
- 不误伤停止按钮、队列按钮等其它图标
- 纯浏览器端样式覆盖，零依赖

## 效果

| 状态 | 图标 |
|---|---|
| 输入内容（激活态） | 🐋 白色/亮色鲸鱼 |
| 空输入（禁用态） | 灰色鲸鱼 |
| 运行中（停止按钮） | 保持原方块图标（不受影响） |

## 安装

### 方式一：本地包安装（当前环境已用）

```bash
# 在 web profile 下安装（本质 pnpm add，会写进 dsh.profile.bundles）
dsh plugin --profile web add <路径>/dsh-external-ds-whale-send-button-0.1.0.tgz

# 验证配置可组合
dsh --profile web --dump-config

# 重启服务生效
```

### 方式二：动态插件（临时，重启即丢）

在「创造模式」会话中用 `cordis_define` 定义 `lib/client.js` 的插件对象并 `cordis_run`。

## 卸载

```bash
dsh plugin --profile web remove @dsh-external/ds-whale-send-button
```

## 工作原理

插件注册为 browser roster 的 client 包（`dsh.client` 字段 + `exports ./client`），
`apply(ctx)` 时向 `document.head` 注入一段 `<style>`（带 `data-plugin-css` 标签，幂等）：

1. 用 `[data-composer-card]` + 发送箭头 path 的唯一 `d` 前缀精确定位主发送按钮；
2. 隐藏原上传箭头 SVG；
3. 用 CSS `mask` 叠加 DeepSeek 官方鲸鱼（取自 dsh 自带 `favicon.svg` 的官方路径），
   `background-color: currentColor` 让鲸鱼颜色随按钮文字色变化。

## 文件结构

```
ds-whale-send-button/
├── package.json          # dsh.client + dsh.bundle.patch 声明
├── cordis.patch.yml      # roster 注册行（bundle patch 自动叠加）
├── lib/
│   ├── client.js         # 浏览器端插件（样式注入）
│   └── index.js          # host 半端占位
└── dsh-external-ds-whale-send-button-0.1.0.tgz  # npm pack 产物
```

## 自定义

改 `lib/client.js` 里的：

- `width/height: 16px` → 图标大小
- `background-color: currentColor` → 固定颜色（如 DeepSeek 蓝 `#4D6BFE`）
- `mask ... contain` → 图标缩放方式

改完重新 `npm pack` 并用 `dsh plugin --profile web add` 升级。

## License

[MIT](./LICENSE)
