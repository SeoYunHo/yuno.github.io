---
layout: post
title: JavaScript에 대한 고찰 2
date: 2017-10-30
excerpt: "JavaScript의 프로토타입에 대해 알아보자"
tags: [js, post, JavaScript 고찰]
comments: true
---

이번에는 JavaScript의 **프로토타입**에 대해서 알아보겠습니다.

## 프로토타입(Prototype)

자바스크립트는 **프로토타입 언어**라고 불리웁니다.

객체지향 언어에는 Class가 있듯이 자바스크립트에는 프로토타입이 있습니다.

그럼 이러한 Prototype을 Class와 비교하면서 알아봅시다.

### Prototype과 Class

다른 객체지향 언어를 공부하셨다면, Class에 대해서 잘 아실 것입니다.

자바스크립트와 다른 객체지향 언어와 비슷합니다.

한가지 다른점은 Class가 아니라 Prototype라는 것입니다.

그래도 자바의 클래스와 Prototype의 다른 점이 있는데 

그것은 class는 새로운 객체를 만들지만,

Prototype은 객체를 복사해서 새로운 객체를 생성합니다.

먼저, 자바에서의 Class는 다음과 같이 사용합니다.

```Java
public Point {
    private int x,y;

    public Point(int x, int y){
        this.x=x;
        this.y=y;
    }

    public void print(){
        System.out.println(x+','+y);
    }
}

//main
Point p1=new Point(10,10);
```

위의 코드를 보면 알 수 있듯이 자바와 같은 객체지향 언어는 

Class를 만들고 new를 통해서 인스턴스를 생성합니다.

그럼 자바스크립트는 어떨까요?

```js
function Point(x, y){
    this.x=x;
    this.y=y;
}

Point.prototype.print=function(){
    console.log(x+','+y);
}

var p1= new Point(0, 0);
```

위의 코드를 보면 이해가 안되는 부분이 있을 것입니다.

좀 더 자세히 알아봅시다.

### Prototype

먼저 아래의 그림을 보면,

![prototype](../img/prototype02.png)

funtion Point()는 자바에서의 생성자와 같은 역할을 하는 함수입니다.

이러한 생성자 함수를 선언하게 되면, 함수가 생성되는 것이 아니라 Prototype Object가 같이 생성되게 됩니다.

그리고 생성된 함수는 prototype이라는 속성을 통해서 이 Object에 접근할 수 있고, 

Prototype Object는 일반 객체와 같고, constructor와 __proto__를 가지고 있습니다.

여기서 constructor는 생성된 함수를 가리키고 있습니다.

그리고 __proto__는 **모든 객체가 가지고 있는 속성**입니다.

```
그런 다음, new를 이용해서 객체를 생성할 수 있는데, 이 때 주의할 점이 있습니다.

바로 new를 깜박하고 사용하지 않았을 때 인데요.

이런 경우에는 객체가 생성되는 것이 아니라 Point라는 함수가 실행되게 됩니다.
```

### __proto__프로퍼티

__proto__는 아래의 그림과 같이 객체가 생성될 때 사용한 생성자 함수의 **Prototype Object**를 가리킵니다.

![prototype](../img/prototype01.png)

그리고 위의 사진을 보면 알 수 있듯이 모든 객체가 마지막으로  __proto__이 가리키는 객체는 Object입니다.

p1에는 x와 y가 없지만 사용할 수 있는 이유가 바로 __proto__때문입니다.

### 프로토타입 체인

p1 객체안에는 실질적으로 x를 직접 가지고 있지 않기 때문에 x 속성을 찾을 때 까지 상위 프로토타입을 탐색합니다.

 이 때 사용하는 것이 __proto__프로퍼티(프로토타입 링크)입니다.

최상위인 Object의 Prototype Object까지 갔지만, x라는 속성이 없는 경우에는 undefined를 리턴합니다. 

이렇게 __proto__속성을 통해 상위 프로토타입과 연결되어있는 형태를 프로토타입 체인(Chain)이라고 합니다.

## 마무리

오늘은 자바스크립트의 프로토타입에 대해서 알아보았습니다.

다음 포스팅에는(아직 정해지지 않았지만..) 좋은 정보를 많이 들고 오도록 하겠습니다!!

그럼 좋은 하루 되시길 바랍니다 :)
