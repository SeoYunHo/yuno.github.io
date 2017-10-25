---
layout: post
title: JavaScript에 대한 고찰 1
date: 2017-10-23
excerpt: "JavaScript의 데이터 타입에 대해 알아보자"
tags: [js, post, JavaScript 고찰]
comments: true
---

이번에는 JavaScript의 데이터 타입에 대해서 알아보겠습니다(최신 ECMAScript 기준).

## 자바스크립트의 타입

ECMA 표준 명세서 5.1 명세에서 타입은 다음과 같이 정의 되어 있습니다.

**"ECMAScript 프로그래머가 ECMAScript 언어를 이용하여 직접 조작하는 값들의 타입이 ECMAScript 언어 타입이다."**

다시 말해서 자바스크립트에서의 **타입**이란 자바스크립트 엔진, 개발자 모두에게 어떤 값을 다른 값으로 분별할 수 있는, 고유한 내부 특성의 집합입니다.

예를 들면, '42'(문자열), 42(숫자)는 서로 다른 값으로 분별할 수 있는 문자열과 숫자가 바로 타입이라는 것입니다.


## 데이터 타입

자바스크립트의 데이터 타입은 기본 자료형과 Object로 나눌 수 있습니다.

- 기본 자료형 (Primitive)
    - Boolean : true와 false
    - Null : null 값 ( *주의: 자바스크립트는 대소문자를 구별하기 때문에 null과 Null, NULL은 서로 다른 뜻을 가지고 있습니다. )
    - Undefined : 값이 없는 변수
    - Number : 수
    - String : 문자열
    - Symbol (ECMAScript 6 에 추가됨)

- Object 자료형

## null과 undefined??

위에서 보면 알겠지만, 자바스크립트의 데이터 타입에는 null과 undefined가 있습니다.

**null과 undefined의 차이는 무엇일까요?**

null은 값이지만, undefined는 값이 할당 안된 것을 말합니다.

**하지만 undefined에서 주의해야할 점이 있습니다.**

바로 다음과 같은 문제입니다.

```js
var a;

console.log(typeof a);      //undefined
console.log(typeof b);      //undefined
```

선언되어있는 변수와 선언되어있지 않은 변수의 typeof 연산자 값이 undefined로 같다는 것입니다.

하지만 같은 undefined 타입이라도 의미하는 바는 당연히 다릅니다.

typeof a의 값인 undefined는 변수 a에는 값이 없다는 뜻이고,

typeof b의 값인 undefined는 변수 b가 없다는 것을 의미합니다.

이 점을 유의해서 사용해야합니다.

**그리고 null에 대해서 조금 재미있는 현상이 있습니다.**

바로 다음과 같이 말이죠

```js
var a = null;
console.log(typeof a);      //object
```

위의 보면 알 수 있듯이 null의 typeof 값이 object입니다.

이것은 처음에 오류였으나 추후에 버전 호환문제 때문에 영원히 수정되지 않을 것 같습니다.

**그렇다면 타입으로 null값을 정확히 확인하려면 어떻게 해야될까요?**

조건을 하나 더 붙여주면 가능합니다.

```js
var a = null;
console.log(!a && typeof a === "object");      //true
```

## 새롭게 추가된 symbol 타입

Symbol 은 ECMAScript 6 에서 추가되었습니다.

Symbol은 유일하고 변경 불가능한 (immutable) 기본값 (primitive value) 이라고 합니다.

Symbol은 이 프로퍼티가 전용/특수/내부 프로퍼티라는 것을 알려주기 위해서 만들어 졌습니다.

따라서 언더스코어(_)가 앞에 붙은 프로퍼티들고 Symbol로 대체될 수 있습니다.

## object 타입

자바스크립트에서 Object는 프로퍼티(속성)를 담는 가방이라고 볼 수 있습니다.

**그렇다면 프로퍼티(속성)은 무엇일까요?**

속성은 객체 리터럴을 통해서 속성들을 초기화 할 수 있고, 이러한 속성들은 추가 제거 할 수 있습니다.

이 속성들은 key 값으로 식별됩니다.(이러한 Key값은 String, Symbol 값입니다.)

속성은 크게 두가지로 분류됩니다.

1. 데이터 속성 
    - 값을 가져오고 설정할 수 있는 속성을 말합니다.
    -  데이터속성은 값을 저장하는 value와 프로퍼티에 값을 저장할 수 있는지 판단하는 Wirtable이 있습니다.
2. 접근자 속성 
    - 접근자 속성은 get, set 2가지 속성이 있습니다. 이것들은 자바의 Getter와 Setter와 비슷하다고 생각하면 쉽습니다.
    - 접근자 속성은 속성 값을 설정하거나 검색할 때마다 사용자가 제공한 함수를 호출합니다.

다시 Object로 돌아오면 Object는 위에서 말했다싶이 키와 값의 매핑입니다.

자바스크립트에서 function도 Object로 취급하는데 function은 호출 가능한 특성을 추가한 Object라고 보면 이해하기 쉽습니다.

## 마무리

오늘은 자바스크립트의 타입에 대해서 알아보았습니다.

다음에는 자바스크립트의 프로토타입에 대해서 알아보겠습니다.

그럼 좋은 하루 되시길 바랍니다 :)
