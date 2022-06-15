---
layout: post
title: [Unity] GetComponentsInChildren
date: 2022-06-15
categorys: Unity
tags: [Unity]
comments: true

---

# [Unity] GetComponentsInChildren

한 오브젝트의 자식 오브젝트들의 배열로 불러오고 싶을때

<mark style='background-color:  #F0AEAF'>GetComponentsInChildren</mark> 을 이용하는데

```c#
GameObject ParentObject;
GameObject[] childrenObject;

void Start()
{ childrenObject=ParentObject.GetComponentsInChildren<GameObject>(true);
}
```

이렇게 사용하니 다음 오류가 발생했다.

`ArgumentException: GetComponent requires that the requested component 'GameObject' derives from MonoBehaviour or Component or is an interface`

GameObject는 MonoBehaviour의 클래스에서 컴포넌트로 사용되지 않기 때문에

<mark style='background-color:#F0CF97'>GetComponentsInChildren<GameObject></MARK>를 사용하지 못한다는 것이다.

그렇기 때문에  다음과 같이 GameObject의 컴포넌트를 사용해주어야 한다.

```c#
GameObject ParentObject;
Transform[] childrenObject;

void Start()
{ childrenObject=ParentObject.GetComponentsInChildren<Transform>();
}
```

또한 GetCompoentsInChildren은 해당 오브젝트나 자식 오브젝트가 비활성화 상태일 때 이용할 수가 없다.

하지만 GetComponentsInChildren<T>()는 includeInactive라는 매개변수를 가지며 디폴트값으로는 false를 가진다.

<mark style='background-color:#F0AEAF'>GetComponentsInChildren<T>(true)</mark>

includeInactive 값을 true로 넘겨준다면 비활성화 되어있는 자식 오브젝트들을 이용할 수 있다.



`참고 https://foxtrotin.tistory.com/145 `