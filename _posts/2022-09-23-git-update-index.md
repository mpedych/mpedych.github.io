---
layout: post
title: "Як надати права на виконання файлу в git"
categories: misc
---

Іноді виникає потреба працюючи в ОС Windows надати файлу права на виконання в Unix-подібних системах. Git дозволяє виконати подібну операцію за допомогою команди:

```shell
git update-index --chmod=+x filename
```
