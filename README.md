# vim-day01
## 今日目标
> 熟悉vim的基本操作
## 安装
>  在vscode中安装vim插件

## normal模式与insert模式
+ 按 `i` 键，从`insert模式` 切换到 `normal模式`，
+ 按 `Ctrl + [` 或者 `esc` 键，从`normal模式` 切换到 `insert模式`

## 基本操作
### 光标移动（在 `normal模式` 下）
+ 按 `h` 键，向 `左` 移动
+ 按 `l` 键，向 `右` 移动
+ 按 `k` 键，向 `上` 移动
+ 按 `l` 键，向 `下` 移动
+ 按 `i` 键，光标前插入，
+ 按 `a` 键，光标后插入

## 扩展
+ 在终端如何使用vim / 如何退出
```powershell
:wq # 保存修改并退出
:q! # 强制退出
```
+ Ctrl和caps位置调换

## 练习
> 尝试修改变量a和b的值和变量名
```js
const a = 1
const b = 2
```

# vim-day02
## 今日目标
> 在单行中更有效率的移动和插入

## 操作（在 `normal模式` 下）
### 1. 移动

+ 按 `shift + o`键，在当前行前新开一行，光标移动至新行的行首并进入编辑模式
+ 按 `^` 键，光标移动至当前行的行首
+ 按 `$` 或者 `g + shift + _` 键，光标移动至当前行的行尾

### 2. 插入
+ 按 `shift + i` 键，行首插入并进入`insert模式`
+ 按 `shift + a` 键，行尾插入并进入`insert模式`
+ 按 `shift + o` 键，行前插入并进入`insert模式`
+ 按 `o` 键，行后插入并进入`insert模式`

### 3. 复制
> 复制当前行，输入 `yy`

### 4. 删除
> 删除当前行，输入 `dd`

### 5. 粘贴
> 粘贴，按 `p` 键

## 练习
```txt
   this is a test       

welcome to China!

```

# vim-day03
## 今日目标
> 掌握vim的语法

## vim语法
> 操作（operation）+ 动词（范围，h、j、k、l、o、g_等）
+ 按 `d + shift + l` 键，删除某个位置到行尾

## 操作
+ 按 `d + 动词` 键，删除
+ 按 `c + 动词` 键，删除并且进入 `insert模式`
+ 按 `y + 动词` 键，复制

## 基于单词 / 字串的移动
+ 按 `e` 键，移动到单词的结尾
+ 按 `b` 键，移动到上一个单词的开头
+ 按 `w` 键，移动到单词的开头
+ 按 `ge` 键，移动到上一个单词的结尾

## 组合
+ `cw`，删除当前单词，输入
+ `ea`，在当前单词结尾处添加

## 练习
```js
function getNameById(params) {
  return `You're a good man`
}
```

# vim-day04
## 今日目标
> 更有效率的处理单字符 & undo/redo

## 操作
+ 按 `x` 键，删除光标所在的字符
+ 按 `shift + x` 键，删除光标前的字符
+ 按 `s` 键，删除当前光标的字符并进入 `insert模式`
+ 按 `shift + s` 键，删除当前光标所行并进入 `insert模式`
+ 按 `r` 键，替换一个字符
+ 按 `shift + r` 键，替换多个字符
+ 按 `u` 键，undo（向前撤销）
+ 按 `Ctrl + r` 键，redo（向后撤销）

## 练习
```js
function getNameById() {
  const obj = {}
  return obj
}
```

# vim-day05
## 今日目标
> 掌握可视化模式

## 操作
### 1. 可视化模式
+ 按 `v` 键，字符
+ 按 `shift + v` 键，行
+ 按 `Ctrl + v` 键，块

### 2. 退出
+ esc 
+ Ctrl + [
+ v
+ V

### 3. 导航
+ 配合动作范围
+ 按 `o` 键，切换可视化的光标位置
+ 按 `g + v` 键，回到上一次选择的选择位置

### 4. 语法
+ 选中 + 操作

### 5. 技巧
+ 多行编辑，按 `Ctrl + v` 键进入多行编辑模式，配合 `shift + a` 键(在光标后编辑) || `shift + i` 键(在光标前编辑) || `d` 键（删除多行光标文字）
+ 复制粘贴（在可视化模式下，按 `Ctrl + c/v` 键，用的是系统的复制/粘贴；输入 `yy` 或者 `p`，使用的是复制/粘贴）
+ 尽可能减少可视化操作（会增加操作步骤）

## 练习
```js
const a-c = 1
const b-c = 2
const c-c = 3


const d-c = 4
```

# vim-day06
## 今日目标
> 掌握文本对象

## 操作
### 1. 认识文本对象
> 文本是结构化的，可以快速选择，可以理解为一个范围

### 2. 语法
+ operator + (内部 `i` / 外部 `a`) + 文本对象
+ 可视化模式`v` + (内部 `i` / 外部 `a`) + 文本对象

### 3. 内部
> 按 `i` 键

### 4. 外部
> 按 `a` 键

### 5. 对象
+ `w` 单词，在 `visual模式` 下，
  + 组合 `i` 键（`viw`，选中当前整个单词）
  + 组合 `a` 键，
    + `vaw`，当单词前后都有空格时，选中的是整个单词 + 后面的空格
    + `vaw`，当单词只有前面有空格时，选中的是整个单词 + 前面的空格
    + `vaw`，当单词没有空格时，选中的只有整个单词
+ `b` 单词，表示 `()` 文本对象，在 `visual模式` 下，
  + 组合 `i` 键，
    + `vib`，选中 `()` 文本对象内的内容
    + `dib`，删除 `()` 文本对象内的内容
  + 组合 `a` 键，
    + `vab`，选中 `()` 文本对象包括 `()` 及其内容
    + `dib`，删除 `()` 文本对象包括 `()` 及其内容
+ `B` 单词，表示 `{}` 文本对象，用法同 `b` 单词
+ `<>`、`[]`、`{}`、`''`、`""` 等用法同 `b` 单词
+ `t` 单词，可以选择xml标签中的内容
+ `s` 单词，表示句子（以 `.`, `!`, `?` 结尾的叫句子）
+ `p` 单词，表示段落 空格间隔开的块
+ vim-textObj-arguments
  + `ia`，不包含分隔符
    + `cia`，删除文本对象并进入 `insert模式`
  + `aa`，包含分隔符
    + `caa`，删除文本对象包含其分隔符
+ vim-textObj-entire
  + `dae`，删除当前文本所有内容
  + `die`，删除当前文本所有内容，但是不包含前面和后面的空格

## 练习
```js
function setName(_name, age) {
  name = _name
  const chan = `chan`
  const chan = "chan"
  const chan = 'chan'
}

setName('BeFend', 26)

this is a command.
this is a command!
this is a command?

<div>this is a test for A</div>
```

# vim-day07
## 今日目标
> 在单文件中更快地移动 

## 操作
+ 滚动
  + 按 `Ctrl + f` 键（forward），向下滚动一屏
  + 按 `Ctrl + b` 键（backward），向上滚动一屏
  + 按 `Ctrl + d` 键，向下滚动半屏
  + 按 `Ctrl + u` 键，向上滚动半屏
  + 按 `Ctrl + e` 键，向下滚动一行
  + 按 `Ctrl + y` 键，向上滚动一行
  + 基于配置（更容易记忆）
    + 按 `shift + k` 键，向上滚动 5 行
    + 按 `shift + j` 键，向下滚动 5 行
    + 按 `shift + k` 键，向上滚动 5 行
+ `zz`，将当前行置于屏幕中央
+ `zt`，将当前行置于屏幕顶部附近
+ `zb`，将当前行置于屏幕底部附近
+ `gg`，跳转到文件首
+ 按 `shift + g` 键，跳转到文件尾
+ 跳转到指定行
  + 行数 + `gg`
  + 行数 + `shift + g`

# vim-day08
## 今日目标
> 掌握搜索

## 操作
### 1. 单行
+ 按 `f` 键，正向移动到下一个{char}所在之处
+ 按 `shift + f` 键，反向移动到上一个{char}所在之处
+ 按 `t` 键，正向移动到下一个{char}所在之处的前一个字符上
+ 按 `shift + t` 键，反向移动到上一个{char}所在之处的后一个字符上
+ 按 `;` 键，重复上次的字符查找命令
  + `fo;`，正向查找当前行 `o` 字符
+ 按 `,` 键，反转反向查找上次的字符查找命令
  + `fo,`，反向查找当前行 `o` 字符
+ 使用技巧
  + 移动的时候用 `f`
  + 结合 `c / d` 键使用 `t`

### 2. 全局，在`visual模式`下，
+ 按 `/` 键，向后查
+ 按 `?` 键，向前查
+ 查找之后，按 `n`键，找下一个匹配内容
+ 查找之后，按 `shift + n` 键，找上一个匹配内容
+ 按 `/` + 方向键，查看搜索历史
+ 按 `/#` 键，向上查光标所在的单词
+ 按 `/*` 键，向下查光标所在的单词

## 练习
```js
Get busy living, Or get busy dying.

Hope is a good thing, maybe the best of things, and no good thing ever dies.

```

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

# vim-day10
## 今日目标
> 认识数字 & 点的威力

## 操作
### 1. 数字
#### 语法
+ 数字 + operation + 动作（范围）
+ operation + 数字 + 动作（范围）

#### 好处
> 保持了连贯的撤销历史记录

#### 坏处
> 需要有思考的时间

### 2. 点
+ 重复上一次的修改
  + 做了更新，包括增加，删除，修改
  + 离开插入模式之前的全部按键操作都记录
+ 在删除一个单词的命令选择上
  + `dbe`，删除光标所在单词的前部分（包括光标所在位置的）文字，并将光标移至单词的尾部
  + `dbx`，删除光标所在单词的前部分（包括光标所在位置的）文字，
  + `diw`，在任意位置上都能删除光标所在位置的单词（`最优操作`）
+ 核心：一键移动 & 一键操作
  + 加分号
    + `La;`，先回到行尾，切换为`insert模式`，加分号
    + `A;`，直接跳转至行尾，切换为`insert模式`，加分号
  + 查找手动替换
+ 能够重复就不要用次数，执行、重复、回退

## 练习
```js
Get busy living, Or get busy dying.

Get busy living, Or get busy dying.;
Get busy living, Or get busy dying.;
Get busy living, Or get busy dying.;
Get busy living, Or get busy dying.;
Get busy living, Or get busy dying.;
Hope is a good thing, maybe the best of things, and no good thing ever dies.

```
# vim-day11
## 今日目标
> 掌握多文件之间的跳转

## 操作
### 1. 定位
+ 标记
  + `m + 小写字母`，单文件标记
  + `m + 大写字母`，多文件标记
+ 跳转
  + `'`，跳转到标记的行
    + *mm'm*
    > 输入 *mm* 标记行，按 *'m* 键之后回到标记行的头部
    + *mM'M*
    > 输入 *mM* 标记当前文件，在其他文件中，按 *'M* 键之后回到标记文件
  + `，跳转到标记的行或列（更精准）
    + *mm`m*
    > 输入 *mm* 标记行，按 *`m* 键之后回到标记行的光标所在位置

### 2. 跳转至定义
+ `gd`， jump to definition

### 3. 跳转
> 任何大于一个单词或超过当前行导航的移动都是一个跳转
+ 命令
  + `'`，跳转到标记的行
  + *`*，跳转到标记的位置（行或列）
  + `gg`，跳转到文件首
  + 按 `shift + g` 键，跳转到文件尾
  + `/`，向后搜索
  + `?`，向前搜索
  + `n`，重复上一次搜索，相同方向
  + `N`，重复上一次搜索，相反方向
  + `gd`，jump to definition
  + `{`，跳转至上一个段落
  + `}`，跳转至下一个段落
  + 不会被记录的命令
    + 翻页
    + `shift + j / k`
  + 特别说明 vim-sneak 的跳转只记录一次

+ 记录跳转
  + vim保留了你移动前位置的记录
  + 使用 :jumps 查看 
+ `Ctrl + i`，向后跳
+ `Ctrl + o`，向前跳 

# vim-day12
## 今日目标
> 处理包裹字符的符号

## 操作
+ vim-surround
  + `c + s + <existing>（替换的对象） + <desired>（替换的内容）`，Change existing surround to desired。
    + `cs"'`，替换句子中 `"` 为 `'`
  + `y + s + <motion>（替换的对象） + <desired>（替换的内容）`，Add desired surround around text defined by。
    + `ysiw{`，为单词增加 `{`
  + `d + s + <existing>`，Delete existing surround。 
    + `ds{`，删除单词的花括号
  + `S + <desired>`，surround when in visual modes(surround full selection)
    + 在visual模式下，选中范围，`S + '`，选中部分将包裹 `'`。 

## 练习
```js
import add from "../add"

const a = `test${hhhh}`
```

# vim-day13
## 今日目标
> 替换字符串

## 操作
### 1. 替换命令:substitute
  *公式（[]内的表示可写可不写）：*
> :[range] (范围) + s[ubstitute] (全称或简称) / {pattern}(模式) / {String} / [flags]
  + `:s/busy/test`，替换里当前行找到的第一个busy为test
+ `range` 为 `%` 时，表示全文
  + `:%s/busy/test`，替换全文中每一行找到的第一个busy为test
+ `range` 为 `number,number` 时，表示从哪一行到哪一行
  + `:503,510s/busy/test`，替换503-510行的busy为test
+ `range` 为 `$` 时，表示到尾部
  + `:503,$s/busy/test`，替换503到文末的busy为test
+ `pattern` 为 `g` 时，表示全文所有的匹配 
  + `:%s/busy/test/g`，替换全文中每一行找到的每一个busy为test
+ `pattern` 为 `c` 时，会弹出一个确认框 
  + `:%s/busy/test/gc`，弹出确认对话框（包括y/n/a/q/l选项）
    + 选择 `y` 时，表示把当前高亮的替换
    + 选择 `n` 时，表示当前高亮的不替换
    + 选择 `a` 时，表示把所有都替换，并退出
    + 选择 `q` 时，表示退出
    + 选择 `l` 时，表示把当前高亮的替换，并退出

### 2. 多选
+ `gb`找到下一个相同的单词并添加另一个光标


## 练习
```js
Get busy living, Or get busy dying.

Get busy living, Or get busy dying.
Get busy living, Or get busy dying.
Get busy living, Or get busy dying.
Get busy living, Or get busy dying.
Get busy living, Or get busy dying.
Hope is a good thing, maybe the best of things, and no good thing ever dies.

```

# vim-day14
## 今日目标
> 掌握悬浮显式 & 大小写 & 注释

## 操作
### 1. 悬浮显示
+ `gh`，悬浮显示

### 2. 大小写
+ 在normal模式下，
  + `gu`，小写
  + `gU`，大写
+ 在`visual模式`下，
  + `u`，小写
  + `U`，大写
+ `~`，大小写互换

### 3. 注释
> normal模式与visual模式通用
+ `gc`，单行注释
+ `gC`，多行注释
