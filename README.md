# vim篇
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

# vim-day15
## 今日目标
> 掌握窗口的管理

## 操作

### 1. vim的窗口管理
#### 新建窗口
+ `Ctrl + w + v`，在当前窗口的左边或右边新建窗口
+ `Ctrl + w + s`，在当前窗口的上边或下边新建窗口

#### 窗口切换
+ `Ctrl + w + h/j/k/l`，切换到上 / 下 / 左 / 右方向的窗口
+ `Ctrl + w + v`，打开多个窗口时，在不同的窗口间相互切换，如只有两个窗口时，则在两个窗口间互相切换

#### 关闭窗口
+ `Ctrl + W + c`，关闭当前窗口
+ `Ctrl + w + o`，只保留当前窗口，关闭其他所有的窗口

### 2. vscode的自定义快捷键
#### 新建窗口
+ `win + \`，在当前窗口的下边新建窗口
+ `win + Ctrl + \`，在当前窗口的上边新建窗口
+ `Ctrl + \`，在当前窗口的右边新建窗口

#### 关闭窗口 
+ `win + w`，关闭当前窗口
+ `win + k + w`，保留当前窗口，关闭其他所有窗口

#### 窗口切换
+ `shift + 方向键`
+ 没改键的话，使用`shift + Ctrl + j/k/h/l`

# vim-day16
## 今日目标
> 如何删除一个函数

## 操作
+ `%`，匹配括号 `()` / `[]` / `{}` 对象
+ vim-indent-object
  + `vii`，选择函数内文本对象范围内的内容
  + `vai`，选择函数对象不包括结尾符号的内容
  + `vaI`，选择整个函数内容
+ `dap / dip`，删除整个函数体内至空白行前部分的代码
+ `daI`，删除整个函数体
+ `V + $ + % + d`，`V` 选中整行后，用 `$ + %` 匹配括号，直至匹配到想要删除的内容，按 `d` 删除

## 映射配置
```json
  "vim.visualModeKeyBindings": [
    {
      "before": ["a", "i"],
      "after": ["a", "I"]
    }
  ],
  "vim.normalModeKeyBindings": [
    {
      "before": ["<Leader>", "d", "f"],
      "after": ["V", "$", "%", "d"]
    }
  ],
  "vim.operatorPendingModeKeyBindings": [
    {
      "before": ["a", "i"],
      "after": ["a", "I"]
    }
  ]
```

## 练习
```js

function setName(name = "test") {
  console.log(name);
}

function getName(name="test", age = 19) {
  const a = "1";
  const b = "2";
  const arr = ["1", "2", "3"];

  if (a === b) {
    console.log("test");
  }
}
```

# vim-day17
## 今日目标
> 掌握宏，宏可以录制一系列动作。

## 操作
### 1. 基础知识
+ `qa`，开始录制，`a` 是寄存器的名字，也可以用别的
+ `q`，结束录制
+ `:reg a`，查看录制好的宏
+ `@a`，使用，`a` 是寄存器的名字
+ `@@`，对于某个宏需要连续调用的话，这个命令十分有用
+ `数字 + @ + 寄存器`，重复执行
  + `qa0f. + enter + r)w~jq`
    + `qa` 启动录制，`a` 是寄存器的名字
    + `0` 回到行首
    + `f.+ 回车` 匹配 `.`
    + `r)` 将匹配到的 `.` 替换成 `)`
    + `w~` 跳到下一个单词首字母，并将字母小写转换成大写
    + `j` 换行
    + `q` 停止录制。

### 2. 扩展知识
+ 安全机制，报错就停
+ `qA`，追加，`A`是之前寄存器的大写
+ 修改一个已知的宏
  + 就是修改寄存器里面的内容
  + 取出来
    + `"ap`，复制出来
    + `:put a`
  + 修改
    + `ayw / ayy`，粘贴进去

### 3. 技巧
+ 先规范好光标的位置
+ 移动的时候使用相对位置
  + 比如 `w / e / textObj / f / t` 都可以
  + 但是 `j / k / h / l` 就是绝对位置
  
## 练习
```txt
1) OperatorPendingModeKeyBindings
2) Two
3. three
4. formatDocument
10. ten
```

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

# vim-day20
## 今日目标
> 操作多个vscode窗口

## 操作

+ 打开新的vscode窗口
  + mac: `shift + command + n`
  + win: `shift + Ctrl + n`

+ 选择工作区，`Ctrl + r`

+ 多个窗口切换
  + mac: *command + `*
  + win: `Alt + Tab`

+ 关闭vscode窗口
  + mac: `shift + command + w`
  + win: `shift + Ctrl + w`

# vim-day21

## 今日目标
> 掌握搜索

## 操作
+ 全局搜索
  + `Ctrl + shift + f`，打开 `vscode` 的全局搜索栏
  + `Ctrl + up/down`，选中搜索栏的输入框
  + `Ctrl + shift + j`，查看搜索内容
+ 查找单一工作空间，
  + `Ctrl + t`
+ 查找单一文件
  + `Ctrl + shift + o` / `Ctrl + p + @`，搜索框出现`@`，搜索变量
  + `Ctrl + p + :`，按照类别分组
+ `Ctrl + shift + p`， 查找命令
+ `Ctrl + p`，快速定位文件
+ 切换文件，
  + `vim环境` 下，两个文件的快速跳转，`Ctrl + i/o`
  + `vscode环境` 下，`Ctrl + Tab`

# vim-day22

## 今日目标
> 编码

## 操作
+ 显示可用的代码操作
  + `mac`环境下，`command + .`
+ 触发参数建议
  + `mac`环境下，`shift + command + space`
  + `win`环境下，`shift + space`（通过修改键盘快捷键）
+ 触发建议
  + `mac`环境下，`command + i`
  + `win`环境下，`Alt + i`
+ 移动行
  + `mac`环境下，`opt + up/down`
  + `win`环境下，`Alt + Ctrl + j/k`
+ 增加行
  + `mac`环境下
    + `command + enter`，在当前光标的下方增加一行
    + `command + shift + enter`，在当前光标的上方增加一行
+ 删除前面的单词
  + `mac`环境下
    + `opt + delete`，删除前面的整个单词
    + `opt + Ctrl + delete`，按照单词去删除
  + `win`环境下
    + `opt + delete`，删除前面的整个单词
    + `opt + Ctrl + delete`，按照单词去删除
+ `F8`，基于整个工作区， 跳转到错误处
+ 选择所有出现的当前单词
  + `mac`环境下，`command + F2`
  + `win`环境下，`Ctrl + F2`
  
## 练习
```js
function getName(name, age) {
  this.name = name
  this.age = age
}

getName()
```

# vim-day23

## 今日目标
> 发现使用快捷键的场景

## 操作
+ 资源管理器
  + `mac`环境下，`command + b`，显示/隐藏资源管理器
  + `win`环境下，`Alt + b`，显示资源管理器
+ 使用`live sever`起服务
  + `mac`环境下，`command + l` + `command + o` 启动服务；`command + l` + `command + c` 关闭服务
  + `win`环境下，`Alt + l` + `Alt + o` 启动服务；`Alt + l` + `Alt + c` 关闭服务
+ 预览 `md`
  + `mac`环境下
    + `command + k + v`，打开侧边预览
    + `command + shift + v`，打开预览
  + `win`环境下
    + `alt + m`，打开侧边预览(通过改键配置)
    + `Ctrl + shift + v`，打开预览
+ 显示扩展
  + `mac`环境下，`command + shift + x`
  + `win`环境下，`Alt + shift + x`
+ 显示真实文件详情
  + `mac`环境下，`command + k + r`
+ 复制活跃文件路径
  + `mac`环境下，`command + k + p`
  + `win`环境下，`Alt + k + p`

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

# vim-day25

## 今日目标
> 学习lazygit

## 安装
> 安装 `lazygit` 后在 `git` 的仓库目录下命令行键入 `lazygit` 即可打开 `lazygit`，也可以在 `~/bash_profile` 中添加别名 `lg`，即添加新一行 `alias lg='lazygit'`；
> *注意：修改 bash_profile 文件前最好先备份该文件！尤其不知道这是什么东西的朋友！*

## 基本操作
+ `q`，退出 lazygit；
+ `h / l`，在左侧由上至下五个功能区焦点切换，也可以通过数字键 1 ~ 5 来切换对应功能区
+ `j / k`，功能区内单条记录焦点切换；如 commit 记录焦点切换，分支焦点切换等
+ `[ / ]`，功能区内有多个标签页的，可以通过这两个命令左右切换；如分支区的 `Local Branches / Remotes / Tags` 这几个标签页的切换
+ `?`，如同 `Vimium-c` 一样，键入 `?` 会弹出当前功能区的所有可用命令以及其功能描述（相同的一个命令，如 a，在不同的功能区其对应的功能也不一样）

## Git常用操作
+ `add`
  + 左栏切换到第二栏 `Files` 栏中，如果是对单个文件进行暂存可以聚焦到对应文件后按下 `space` 键即可；而如果是要对所有文暂存则可以按 `a`；而如果当前文件或者所有文件都已暂存，这时使用 `space / a` 会变回为未添加到暂存的状态
+ `commit`
  + 左栏切换到第二栏 `files` 栏中，按 `c` 会弹出输入框要求填入提交信息，输入后 `enter` 即可提交已经暂存的更改；如果是需要添加详细可以使用 `C`
+ `reset`
  + 左栏切换到第四栏 `Commits` 栏中，切换聚焦需要回退到的那个提交上，键入 `g`，会有弹框可选择 `reset` 的 `--soft / --mixed / --hard` 参数，`enter` 即可选择
+ `pull`
  + 在任意位置都可通过 `p` 进行代码拉取，会拉取左栏第三栏中的 `Local Branches` 的分支列表中的带星号的分支的远程分支代码
+ `push`
  + 在任意位置都可通过 `P` 进行代码推送，会推送代码到左栏第三栏中的 `Local Branches` 的分支列表中的带星号的分支的远程分支中
+ `discard`
  + 需要撤销更改时，左栏切换到第二栏 `Files` 栏中，聚焦要撤销的文件，键入 `d` 即会弹出提示框提示是否撤销该文件所有更改；如果是要把当前项目中的所有文件的更改一并撤销，则可以键入 `D` 后选择需要撤销的类型
+ `branch`
  + 在左栏切换到第三栏 `Local Branches` 栏中，键入 `n` 即可基于当前分支创建新分支，键入 `d` 即可删除聚焦的分支

# vim-day26

## 今日目标
> 掌握snippets

## 插件
> vscode 中常用的 snippets 插件：
>
> [JavaScript (ES6) code snippets](https://marketplace.visualstudio.com/items?itemName=xabikos.JavaScriptSnippets)
>
> [Vue 3 Snippets](https://marketplace.visualstudio.com/items?itemName=hollowtree.vue-snippets)
>
> [Vue VSCode Snippets](https://marketplace.visualstudio.com/items?itemName=sdras.vue-vscode-snippets)
+ JavaScript(ES6) code snippets

## 常用Snippets指令
 trigger | content
 :----: | :----:
imp | imports entire module import fs from 'fs'
imd |	imports only a portion of the module using destructing import {rename} from 'fs'
anfn |	creates an anonymous function (params) => {}
nfn |	creates a named function const add = (params) => {}
clg |	console log console.log(object)
rp | return new Promise()
... | ...

## 配置自己的 Snippets

# vim-day27

## 今日目标
> 掌握重构

## 插件
> 常用的重构工具：
>
> [Abracadabra](https://marketplace.visualstudio.com/items?itemName=nicoespeon.abracadabra)
>
> [Hocus Pocus](https://marketplace.visualstudio.com/items?itemName=nicoespeon.hocus-pocus)
>
> [JavaScript Bootster](https://marketplace.visualstudio.com/items?itemName=sburg.vscode-javascript-booster)

## vscode自带重构指令
+ `Ctrl + shift + r`，只会出现和重构相关的提示
+ `ctrl + .`， 出现所有提示
+ [vscode自带的重构文档](https://code.visualstudio.com/docs/typescript/typescript-refactoring)
+ `Extract Method`，提炼方法
+ `Extract Variable`，提炼变量
+ `空格 + r + n`，重命名  

## 插件
+ [Abracadabra](https://marketplace.visualstudio.com/items?itemName=nicoespeon.abracadabra)
  + 提炼变量
  + 转换模板字符串

+ [Hocus Pocus](https://marketplace.visualstudio.com/items?itemName=nicoespeon.hocus-pocus)
  + `<Leader> + f + f`，创建函数（通过改键设置）
  + `<Leader> + r + e`，提取变量
  + `<Leader> + v + v`，创建变量
```json
    "vim.normalModeKeyBindingsNonRecursive": [
        // 插件Hocus Pocus 快捷键 创建变量
        {
            "before":["<Leader>", "v","v"],
            "commands":["hocusPocus.createVariable"]
        },
        // 插件Hocus Pocus 快捷键 创建函数
        {
            "before":["<Leader>", "f","f"],
            "commands":["hocusPocus.createFunction"]
        }
    ],
```

+ [JavaScript Bootster](https://marketplace.visualstudio.com/items?itemName=sburg.vscode-javascript-booster)
  + 和Abracadabra
  + 箭头函数转换
  + 三目运算符转换