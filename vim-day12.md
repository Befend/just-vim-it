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
