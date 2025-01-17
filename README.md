<div align="center">


# OneDice

**通用掷骰串标准**  
**Our differences shall become our strength**  
**Today, we stand as one**  

</div>

## 概述

OneDice 意为 **通用掷骰串标准** ，是一个面向计算机行业的数学表达式标准，旨在统一不同用户级随机数描述时所涉及的应用交互界面设计，使开发者们无需在这类细枝末节的设计中浪费精力或相互争吵，乃至产生过多不合理设计；亦可使用户在使用不同开发者所开发的产品时，能够拥有一个更便捷直接、符合直觉且功能强大的统一表达方式。

## 背景

OneDice标准的来源并无一个最基本的追溯，起初它只是各类**TRPG**（**T**abletop **R**ole-**p**laying **g**ame）规则书中一种描述由多种面数实体骰子所组成的掷骰组合并试图达成某种随机数分布，以实现规则书下的游戏性，而约定俗成的一种表述方式。  
而TRPG中的一大类型——**跑团**，正是一种将这类表述方式在游戏过程中发挥到极致的类别，一场跑团游戏中，通常会用到种类繁多的掷骰组合，以至于需要随时用这种表述方式指明所需要掷骰的详细组合。  
但是，随着互联网技术的普及，原先以面对面家庭聚会为主进行的跑团游戏也被推广至了电子邮件、论坛、即时通讯等一系列以交互为主的社交方式中，同时，在这些社交媒体中新兴的一类用于模拟原先掷骰行为的各类软件则需要面对高频、复杂、丰富的掷骰表述方式，在这个以社区为主要驱动的开发历程中，这种表述方式被逐渐称为——**掷骰串（掷骰表达式）**  
掷骰串这种描述方式最终表现为：以一种扩展初等代数的方式，引入诸如：  
**d**（classic **d**ice）—— 普通多面掷骰  
**a**（**a**dding dice）—— 无限加骰池  
**c**（double **c**ross adding dice）—— 双重十字加骰池  
**f**（**f**ate dice）—— FATE掷骰池  
等此类以字母标识的运算符，并辅助以一些标定参数，实现诸如：  
`2d20` —— 骰出**2**个**20**面骰，求其**和**  
`7a5m6k4` —— 进行初始为**7**个**6**面骰且加骰线为**5**的普通加骰骰池，计算不低于**4**的骰子**个数**  
这类的表述效果。  
随着各开发者的深入工作与充分交流，相关领域的需求被逐渐探索清楚，开发者与用户已经不再满足于各自为阵对掷骰串进行定义与使用，一个统一的掷骰串标准已经被提上日程。  
最终，在多数开发者的共同努力下，一个统一的精确标准已经被正式提出，我们将其称为OneDice。

## 愿景

在此，我们提出 OneDice V1 版本的标准描述。  
我们的愿景是未来的开发者与用户可以在各类涉及此类由多种骰子与掷骰方式所组合而成的描述中灵活的应用这一统一的标准，降低开发与学习成本，使得社区活动可以将更多的注意力放在更具有独特性价值的事业中。  

## 支持骰系

[OlivaDice](https://github.com/OlivOS-Team/OlivaDiceCore)  
[ZhaoDice](https://github.com/zhaodice/diceApp)  
[SinaNyaDice](https://sinanya.com)

## 参考

官方标准库[onedice.py](https://github.com/OlivOS-Team/onedice.py)  
