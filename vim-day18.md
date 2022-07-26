# vim-day18
## 今日目标
> vim调用vscode的命令

## 操作
### 1. command字段
> 配置修改
```json
  "vim.normalModeKeyBindingsNonRecursive": [
    // 格式化文档
    {
      "before": ["<Leader>", "f", "d"],
      "commands": ["editor.action.formatDocument"]
    },
    // 重命名文档
    {
      "before": ["<Leader>", "r", "n"],
      "commands": ["editor.action.rename"]
    },
    // 折叠代码
    {
      "before": ["<Leader>", "["],
      "commands": [
        {
          "command": "editor.fold"
        }
      ]
    },
    {
      "before": ["<Leader>", "]"],
      "commands": [
        {
          "command": "editor.unfold"
        },
        {
          "command": "vim.remap",
          "args": {
            "after": ["$", "%"]
          }
        }
      ]
    }
  ]
```
### 2. 功能点
+ 格式化文档
  + `shift + alt + f`
  + `<Leader> + f + d`

+ 重命名
  + `f2`
  + `<Leader> + r + n`

+ 折叠代码
  + `alt + cmd + [`
  + `<Leader> + [`  