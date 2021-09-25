---
layout: post
title: GetComponent, FindObjectOfType
date: 2021-09-25
categories: Unity
tags: [Unity, GetComponent, FindObjectOfType]
---

# GetComponent, FindObjectOfType

### GetComponet

 특정 object의 component를 찾음

```c#
GameObject object;
object.GetComponent<SpriteRenderer>();
//object의 component인 SpriteRenderer을 찾음
```

### FindObjectOfType

hierarchy창에 있는 모든 object들을 검색 `검색된 object script 함수 사용`

```c#
GameManager gameManager = FindObjectOfType<objectManager>();
//object의 script인 objectManager를 찾음
```

