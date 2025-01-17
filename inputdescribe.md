# OneDice 输入标准

## 运算符

### 普通多面掷骰 d
```
AdB(kq)C(pb)D
```
#### 简述
这是最基础的掷骰方式，即为掷`A`个面数为`B`的多面骰子，然后计算它们（全部或部分）的点数总和，即为该表达式的最终结果。  

#### 参数介绍
 符号 | 参数 | 名称 | 解释 | 缺省 | 类别
 :---: | :---: | :--- | :--- | :--- | :---
 d | A | 骰数 | 掷出多少个骰子 | 1 | 左值
 d | B | 面数 | 掷出的骰子有多少面 | - | 右值
 k/q | C | 选取线 | 只选取最大/小骰子</br>结果的个数，k大q小 | A | 参数
 p/b | D | 奖惩数 | 追加奖惩骰的个数 | 0 | 参数

#### 附加说明
 - 面数`B`的缺省值通常由规则书决定，例如DND中通常为`20`，而COC中通常为`100`
 - `p/b`符号的奖惩骰规则来自COC，详见`惩罚骰/奖励骰`，该参数将强制覆写`B`为`100`，并对`A`个骰子中每一只都进行`C`个该操作
 - `k/q`符号与`p/b`符号不可同时使用


### 惩罚骰/奖励骰 p/b
```
A(pb)B
```
#### 简述
这是来自COC的掷骰方式，即为掷`1`个面数为`100`的多面骰子(实质上为：范围`1~10`的`10`面个位骰；范围`0~9`的`10`面十位骰，其中通常将普通`10`面骰的`10`计为`0`)，再掷`B`个面数为`10`的`惩罚骰/奖励骰`，用其中`最大/最小`点数替换原先的十位骰，然后计算它们（全部或部分）的点数总和，即为该表达式的最终结果。  

#### 参数介绍
 符号 | 参数 | 名称 | 解释 | 缺省 | 类别
 :---: | :---: | :--- | :--- | :--- | :---
 p/b | A | - | 无意义 | 1 | 左值
 p/b | B | 面数 | 追加奖惩骰的个数 | 1 | 右值


### 无限加骰池 a
```
AaBkCmD
```
#### 简述
这是常见于无限规则的掷骰方式，即为掷`A`个面数为`D`的多面骰子，计算点数不低于`B`的骰子个数，然后以此为新的骰子个数进行下一轮掷骰，直到下一轮掷骰不存在，然后求出所有累计结果中点数不低于`C`的骰子个数，即为该表达式的最终结果。  

#### 参数介绍
 符号 | 参数 | 名称 | 解释 | 缺省 | 类别
 :---: | :---: | :--- | :--- | :--- | :---
 a | A | 初始骰数 | 第一轮掷出多少个骰子 | - | 左值
 a | B | 加骰线 | 每有一枚不低于该值</br>则下一轮掷骰增加一枚骰子 | - | 右值
 k | C | 成功线 | 最终计算不低于该参数的骰子个数 | 8 | 参数
 m | D | 面数 | 掷出的骰子有多少面 | 10 | 参数


### 双重十字加骰池 c
```
AcBmC
```
#### 简述
这是常见于双重十字规则的掷骰方式，即为掷`A`个面数为`C`的多面骰子，计算点数不低于`B`的骰子个数，然后以此为新的骰子个数进行下一轮掷骰，直到下一轮掷骰不存在，最后一轮记其最大值，此前每一轮记为`C`点，然后累加每一轮的点数总和。  

#### 参数介绍
 符号 | 参数 | 名称 | 解释 | 缺省 | 类别
 :---: | :---: | :--- | :--- | :--- | :---
 c | A | 初始骰数 | 第一轮掷出多少个骰子 | - | 左值
 c | B | 加骰线 | 每有一枚不低于该值</br>则下一轮掷骰增加一枚骰子 | - | 右值
 m | C | 面数 | 掷出的骰子有多少面 | 10 | 参数


### FATE掷骰池 f
```
AfB
```
#### 简述
这是常见于FATE规则的掷骰方式，即为掷`A`个面数为`3`的多面骰子，该骰子的三面分别为`+`/`-`/`0`，分别计为`1`、`-1`、`0`，计算所有骰子点数总和，即为该表达式的最终结果。  

#### 参数介绍
 符号 | 参数 | 名称 | 解释 | 缺省 | 类别
 :---: | :---: | :--- | :--- | :--- | :---
 f | A | 骰数 | 掷出多少个骰子 | 4 | 左值
 f | B | - | 无意义 | 3 | 右值


## 运算法则

### 初等代数
除了上一节所包括的各类扩展运算符，还支持进行初等代数相关的运算。
 符号 | 名称 | 备注
 :---: | :---: | :---
 `+` | 加法 | -
 `-` | 减法 | -
 `*`</br>x | 乘法 | -
 / | 除法 | 只取整数部分
 ^ | 幂 | -
 ( | 左括号 | 详见运算优先级
 ) | 右括号 | 详见运算优先级


### 运算优先级
当不存在括号`(`、`)`时，表达式中的初等运算符遵守从左往右，从优先级高到优先级低的运算方式，优先级等级如下：
 符号 | 等级
 :---: | :---:
 `+` | 1
 `-` | 1
 `*`</br>x | 2
 / | 2
 ^ | 3
 d | 4
 a | 4
 c | 4
 f | 4
 ( | -
 ) | -

当存在括号的时候，括号内的表达式优先计算。
