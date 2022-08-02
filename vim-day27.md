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


