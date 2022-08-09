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