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
