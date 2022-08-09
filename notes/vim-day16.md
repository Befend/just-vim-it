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