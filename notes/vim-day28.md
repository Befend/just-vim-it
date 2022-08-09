# vim-day28

## 今日目标
> 学习插件 [`VSpaceCode`](https://vspacecode.github.io/docs/)

## 安装地址
> [https://marketplace.visualstudio.com/items?itemName=VSpaceCode.vspacecode](https://marketplace.visualstudio.com/items?itemName=VSpaceCode.vspacecode)

## 初始化
> [setting.json](https://github.com/VSpaceCode/VSpaceCode/blob/master/src/configuration/settings.jsonc)
```json
    "vim.normalModeKeyBindingsNonRecursive": [
        {
            "before": ["<space>", ";"],
            "commands": ["vspacecode.space"]
        }
    ],
```

> [keybindings.json](https://github.com/VSpaceCode/VSpaceCode/blob/master/src/configuration/keybindings.jsonc)
```json
[
    // Trigger vspacecode in empty editor group
    {
        "key": "space",
        "command": "vspacecode.space",
        "when": "activeEditorGroupEmpty && focusedView == '' && !whichkeyActive && !inputFocus"
    },
    // Trigger vspacecode when sidebar is in focus
    {
        "key": "space",
        "command": "vspacecode.space",
        "when": "sideBarFocus && !inputFocus && !whichkeyActive"
    }
]
```

## 在原有基础上做修改
### 修改/增加
```json
  "vspacecode.bindingOverrides": [
    {
      "keys": "g.s",
      "name": "Go to line",
      "type": "command",
      "command": "workbench.action.gotoLine"
    }
  ],
```

### 删除
```json
  "vspacecode.bindingOverrides": [
    {
      "keys": "g.s",
      "position": -1
    }
  ],
```

### 重写
```json
  "vspacecode.bindingOverrides": [
    {
      "keys": "g",
      "name": "Go...",
      "type": "bindings",
      "bindings": [
        {
          "keys": "g",
          "name": "Go to",
          "type": "command",
          "command": "workbench.action.gotoLine" 
        }
      ]
    }
  ],  
```

### 定义自己的
```json
  "vspacecode.bindings": [
    {
      "key": "g",
      "name": "Go...",
      "type": "bindings",
      "bindings": [
        {
          "key": "g",
          "name": "Go to",
          "type": "command",
          "command": "workbench.action.gotoLine" 
        }
      ]
    }
  ],
```

## 扩展
> 自己配置vim，可以参考原有的[`vscode-vim的配置`](https://github.com/VSpaceCode/VSpaceCode/tree/vscode-vim)