# vim-day24

## 今日目标
> 搞定git

## 操作
```json
  "vim.normalModeKeyBindingsNonRecursive": [
    {
      "before": ["<Leader>", "g", "c", "l"],
      "commands": ["git.clean"]
    },
    {
      "before": ["<Leader>", "g", "d", "f"],
      "commands": ["git.openChange"]
    },
    {
      "before": ["<Leader>", "g", "c"],
      "commands": ["git.commit"]
    },
    {
      "before": ["<Leader>", "g", "s"],
      "commands": ["git.stage"]
    },
    {
      "before": ["<Leader>", "g", "u"],
      "commands": ["git.unstage"]
    },
    {
      "before": ["<Leader>", "g", "g"],
      "commands": ["workbench.view.scm"]
    }
  ]
```
+ `<Leader> + g + g`，显示资源改变面板
+ `<Leader> + g + s`，文件暂存更改
+ `<Leader> + g + c`，显示资源改变面板
+ `<Leader> + g + f`，显示资源改变面板
+ `<Leader> + g + u`，取消文件暂存更改
+ `<Leader> + g + c + l`，清除文件改变

## 扩展
+ `edamagit`插件