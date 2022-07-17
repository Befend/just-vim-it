# vim-day09
## 今日目标
> 更高效地移动，想去哪里就去哪里 

## 操作
### 1. vim-easymotion
> 通过修改 `vscode` 的 `setting.json` 文件
```json
    "vim.easymotion": true,
    "vim.leader": "<Space>" // 以空格代替leader
```

+ `<leader><leader>w`，向前（向下）查找高亮可跳转单词的头
+ `<leader><leader>b`，向后（向上）查找高亮可跳转单词的头
+ `<leader><leader>e`，向前（向下）查找高亮可跳转单词的尾
+ `<leader><leader>ge`，向后（向上）查找高亮可跳转单词的尾
+ `<leader><leader>j`，向前（向下）查找高亮可跳转行的头
+ `<leader><leader>k`，向后（向上）查找高亮可跳转行的头
+ `<leader><leader>l`，向前（向下）匹配并高亮出所有的跳转点（包括单词的开头和结尾，大小写，_和#）
+ `<leader><leader>h`，向后（向上）匹配并高亮出所有的跳转点（包括单词的开头和结尾，大小写，_和#）

### 2. vim-sneak
> 通过修改 `vscode` 的 `setting.json` 文件
```json
    "vim.sneak": true，
    "vim.normalModeKeyBindingsNonRecursive": [
      // format document
      {
        "before": ["<Leader>", "f"],
        "commands": ["editor.action.formatDocument"]
      },
      // jump to error
      {
        "before": ["<Leader>", "e"],
        "commands": ["editor.action.marker.nextInFiles"]
      },
      {
        "before": ["J"],
        "after": ["5", "j"]
      },
      {
        "before": ["K"],
        "after": ["5", "k"]
      },
      {
        "before": ["f"],
        "after": ["s"]
      },
      {
        "before": ["F"],
        "after": ["S"]
      },
      {
        "before": ["s"],
        "after": ["c", "l"]
      },
      {
        "before": ["S"],
        "after": ["^", "C"]
      },
    ],
    "vim.operatorPendingModeKeyBindings": [
      {
        "before": ["f"],
        "after": ["z"]
      },
      {
        "before": ["F"],
        "after": ["Z"]
      }
    ],
    "vim.visualModeKeyBindingsNonRecursive": [
      {
        "before": ["f"],
        "after": ["s"]
      },
      {
        "before": ["F"],
        "after": ["S"]
      },
    ],
```

+ 按 `s` + 两个字符
  + `sea`，向前（向下）查找包含 `ea` 的所有可跳转点，此时再按 `;` 键是向前（向下）查找，按 `,` 键是向后（向上）查找
+ 按 `S` + 两个字符
  + `Sea`，向后（向上）查找包含 `ea` 的所有可跳转点，此时再按 `;` 键是向后（向上）查找，按 `,` 键是向前（向下）查找
+ 改键，通过修改 `vscode` 的 `setting.json` 文件，用 `s` 和 `S` 键来映射原有的 `f` 和 `F` 键，为避免出现递归，原有的 `s` 和 `S` 键也要进行替换。
+ `visual模式 / normal模式` 下，按 `f` / `F` + 两个字符
  + `fea`，向前（向下）查找包含 `ea` 的所有可跳转单词
  + `Fea`，向后（向上）查找包含 `ea` 的所有可跳转单词
+ operation + z + 两个字符
