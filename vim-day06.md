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
