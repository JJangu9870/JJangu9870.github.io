---
layout: post
title: DesignPattern - Observer
image: ObserverPatten_diagram.png
date: 2020-11-22 10:00:00 +0900
tags:
categories: DesignPattern
---
> 옵저버 패턴(Observer Pattern) - 한 객체의 상태가 바뀌면 그 객체에 의존하는 다른 객체들에게 연락이 가고 자동으로 내용이 갱신되는 방식으로 일대다(one to many) 의 의존성을 정의한다.

***

일대다 관계는 주제와 옵저버에 의해 정의됩니다. (옵저버는 주제에 의존)
주제의 상태가 바뀌면 옵저버에게 연락이 가는 형태.

옵저버 패턴에서 상태를 저장하고 지배하는 것은 주제(Subject) 객체!
그러나 옵저버는 반드시 상태를 가지고 있을 필요가 없음. 여러개의 옵저버가 존재할 수 있고, 주제 객체의 상태변화를 기다리는,
주제에 의존적인 성질을 가지게 됨. 그러므로 하나의 주제와 여러개의 옵저버가 연관된 일대다(one to many) 관계가 성립됩니다.

#### Loose Coupling
두 객체가 느슨하게 결합되어 있다는 것은, 둘이 상호작용을 하지만 서로에 대해 잘 모른다는 것을 의미.
옵저버 패턴은 주제와 옵저버가 느슨하게 결합되어 있는 객체 디자인을 제공함.

* 주제 입장 : 옵저버가 Observer인터페이스를 구현하는 것은 알고있음.
* 옵저버 입장 : Observer인터페이스를 구현하고 update가 일어나는 것을 기다림.
 → 옵저버는 언제든지 인터페이스를 구현함으로서 새롭게 추가가 가능하고, 마찬가지로 제거도 가능함.

#### Observable 을 구현한 ClassDiagram - WeatherStation
![]({{site.baseurl}}/images/ObserverPatten_diagram.png)

***

##### Subject - extends Observable
> 주제 역할을 하는 클래스(상태가 들어있음). 데이터의 주인. 데이터가 변경되었을 때 옵저버에게 noti를 해준다. 따라서 옵저버는 주제에게 의존성을 가진다.

<script src="https://gist.github.com/JJangu9870/56af111ec1433ed86b42b000ffd83fff.js"></script>


##### Observer - implements Observer
> 옵저버. 주제 객체에서 상태가 바뀌었다는 것을 알려주기를 기다린다. 하나의 주제에 여러개의 옵저버가 연관된 일대다(one to many)의 관계가 성립된다.

<script src="https://gist.github.com/JJangu9870/b8fa12f29c21343881f7db850024f04b.js"></script>


***
