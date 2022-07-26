# vscode篇
# vim-day19
## 今日目标
> 操作文件

## 操作
### 1. 切到`ﬁles explorer`区域 和 切到`editor`区域
+ `Ctrl+;`，切换到资源管理器,光标在文件编辑区可切换到资源管理器，光标在终端区也可切换到资源

管理器，光标在资源管理器可切换到文件编辑区。
在`keybindings.json`中配置键
```json
    {
        "key": "ctrl+;",
        "command": "workbench.view.explorer",
        "when": "viewContainer.workbench.view.explorer.enabled"
    },
```
### 2. 在`ﬁles explorer` (资源管理器)移动光标、折叠/展开
  + `j`向下移动
  + `k`向上移动
  + `h`跳到当前文件的根目录位置
  + `l`展开文件夹或打开文件
  + `hh/hl` 折叠当前文件夹 
### 3. 创建文件和创建文件夹
#### 在`ﬁles explorer` 资源管理器中：
+ 创建文件，在资源管理器中文件所在位置按`a` 创建文件
在`keybindings.json`中配置键
```json
    {
        "key": "a",
        "command": "explorer.newFile",
        "when": "filesExplorerFocus && !inputFocus"
    },
```
+ `shift+a`创建文件夹，在资源管理器中想要创建的文件夹的位置按`shift+a` 创建文件夹
在`keybindings.json`中配置键
```json
    {
        "key": "a",
        "command": "explorer.newFile",
        "when": "filesExplorerFocus && !inputFocus"
    },
```
#### 在`editor 编辑区`：
+ `<Leader>+n+f`，创建文件，
+ `<Leader>+n+d`, 创建文件夹，
在编辑区突然想在当前文件在创建文件夹或者文件时，可配置vim快捷键
```json
   "vim.normalModeKeyBindingsNonRecursive": [ 
      {
         "before": ["<Leader>", "n", "d"],
         "commands": ["explorer.newFolder"]
      },
      {
        "before": ["<Leader>", "n", "f"],
        "commands": ["explorer.newFile"]
      },
   ]
```
+ `ctrl+n`创建文件 ，vscode自带的
+ 使⽤插件 ﬁle Utils
### 4. 重命名和删除文件
+ `r`，重命名文件
+ `d`，删除文件
在`keybindings.json`中配置键
```json
    {
        "key": "r",
        "command": "renameFile",
        "when": "explorerViewletVisible && filesExplorerFocus && !explorerResourceIsRoot && !explorerResourceReadonly && !inputFocus"
    },
    {
        "key": "d",
        "command": "deleteFile",
        "when": "explorerViewletVisible && filesExplorerFocus && !explorerResourceReadonly && !inputFocus"
    }
```