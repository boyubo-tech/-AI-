# Windsurf 关闭自动运行命令教程

## 🔴 问题
每次 AI 要执行命令时，都会弹出 "Run" 提示框

## ✅ 解决方案

### 步骤 1：打开设置文件
1. 按 `Ctrl + Shift + P` 
2. 输入 `json`
3. 选择 **"Preferences: Open User Settings (JSON)"**

### 步骤 2：修改配置
找到这 3 处，把 `false` 改成 `true`：

```json
"cascade": {
    "confirmOnExecute": true,      // ← 改这里
    "confirmOnBatchEdit": true,    // ← 改这里
}
```

```json
"terminal.integrated.confirmOnRun": true,  // ← 改这里
```

### 步骤 3：保存
按 `Ctrl + S` 保存

---

## 🎯 完整配置参考

```json
{
    "window.commandCenter": true,
    "cursor.general.disableHttp2": true,
    "files.autoSave": "afterDelay",
    "workbench.colorTheme": "Default Dark Modern",
    "window.customTitleBarVisibility": "windowed",
    "cursor.general.disableHttpISSC": true,
    "terminal.integrated.defaultProfile.windows": "Command Prompt",
    "remote.SSH.remotePlatform": {
        "kanban": "linux"
    },
    "ai": {
        "customModels": [
            {
                "name": "GLM-5",
                "model": "glm-5",
                "api": "openai-completions",
                "endpoint": "https://open.bigmodel.cn/api/paas/v4/chat/completions",
                "apiKey": "你的API密钥",
                "temperature": 0.7,
                "maxTokens": 4096
            }
        ],
        "cascade": {
            "model": "GLM-5",
            "confirmOnExecute": true,        ✅
            "confirmOnBatchEdit": true,      ✅
            "confirmOnAcceptChanges": false
        }
    },
    "terminal.integrated.confirmOnRun": true,  ✅
    "terminal.integrated.confirmOnPaste": false,
    "cursor.cascade.confirmOnExecute": false,
    "cursor.cascade.confirmOnBatchEdit": false,
    "cursor.cascade.confirmOnAcceptChanges": false
}
```

---

## 📌 核心要点

| 设置项 | 作用 | 推荐值 |
|--------|------|--------|
| `confirmOnExecute` | 执行命令前确认 | `true` |
| `confirmOnBatchEdit` | 批量编辑前确认 | `true` |
| `confirmOnRun` | 终端运行前确认 | `true` |

---

## ⚡ 快速操作

1. `Ctrl + Shift + P` → 输入 `json` → 选择用户设置
2. 修改 3 处 `false` 为 `true`
3. `Ctrl + S` 保存
4. ✅ 完成！
