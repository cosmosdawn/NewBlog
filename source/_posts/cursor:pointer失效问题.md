---
title: cursor:pointer失效问题
---

在div的css样式中使用cursor:pointer，却发现仅在空白处（padding）能显示手的形状

解决办法：添加z-index

在cep中左侧菜单的收起/展开的“小手柄”上添加z-index之后，点击精确度大幅提升。百发百中！🎯

![Image.png](https://res.craft.do/user/full/3242453e-de37-8f58-f82c-0e73b3c97098/doc/862A328B-7AB4-45B3-B838-5F5C6B81B872/D6D7BB16-9887-420E-B452-0CC767455D5C_2/iC4uXx7KLBpieRQ8jqiLhLq27ZfkML0zjVYvrc7MGDMz/Image.png)

