---
title: 刷题常用模板
published: 2023-05-13
description: "Leetcode template"
image: ""
tags: [刷题, Coding]
category: Note
draft: true
---

## 常用刷题模板

### 回溯

```c++
void backtrack(...args) {
    if(终止条件) {
        存放结果; // res.push(path);
        return;
    }

    for(本层集合中的元素) {
        处理节点;
        backtrack(路径, 选择列表); // 递归
        还原节点;
    }
}
```
