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
