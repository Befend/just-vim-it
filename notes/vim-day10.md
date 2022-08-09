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
