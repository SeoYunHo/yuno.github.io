---
layout: post
title: TDD, Pull-request, 회고회의에 대해서 2
date: 2017-08-02
excerpt: "Pull-request 대해서 알아봅시다!"
tags: [ab180, post]
comments: true
---

저번에는 **TDD**라는 **테스트 주도 방법론**에 대해서 알아보았습니다.

이번에는 **Pull-request**에 대해서 알아보겠습니다.


## Pull-request
---

**Pull-request**라는 용어를 설명드리기 전에 Git이라는 형상 관리 도구에 대해서 아셔야 합니다.

Git에 대해서는 소프트웨어에 관심 있으신 분이라면 한번쯤은 사용해 보셨을 것입니다.

하지만 모르시는 분을 위해서 **Git**에 대해서 간단하게 설명드리고 넘어가겠습니다.


**(Git에 대해서는 추후에 포스팅을 하도록 하겠습니다. 이해가 안되시는 분은 Git에 대한 포스팅을 보시고 봐주시길 바랍니다.)**

### Git?
---

- 소프트웨어를 중심으로 하는 프로젝트에서 빈번하게 발생하는 문제를 해결하기 위해 등장한 도구가 바로 **Git,형상 관리 도구(Configuration Management Tool)**입니다. 

그렇다면 이제부터 본격적으로 **Pull-request**에 대해서 알아봅시다.

**Pull-request**는 간단합니다. **Fork**한 저장소에 **Push**하고 나면 프로젝트 관리자에게 이 내용을 알려야 하는데 이를 **Pull-request**라고 말합니다.

### "위의 말이 이해가 안되시나요??"

조금 더 쉽게 설명하자면, 누군가가 GitHub에 올린 오픈소스 프로젝트에서 **바꿔야할 점**을 발견했을 때, 이를 **Fork**하고, 고친 뒤 다시 **Push**를 합니다. 

하지만 **Push한 내용**은 바로 적용되는 것이 아니라 해당 오픈소스 프로젝트의 **contributer**들이 확인 후 **Merge**를 해야 적용됩니다.

여기서 **Push**를 하고 해당 오픈소스 프로젝트의 **contributer**들에게 알리는 것이 **Pull-request**입니다.

## 마무리
---
GitHub를 통해서 많은 활동은 했지만, 오픈소스에 기여를 한 적은 아직 없습니다. 이번에 Pull-request에 대해서 알아보면서 저도 앞으로는 GitHub에서 오픈소스 프로젝트에 기여를 많이 해야겠다는 생각을 했습니다.

앞으로는 GitHub에서 오픈소스 프로젝트에 기여하는 것에 대해서 포스팅을 할까 생각 중입니다.

### 노력하는 저를 응원해주세요!! :)

### 출처
---

```
Pull-request
- https://www.slideshare.net/jungseobshin/github-pull-request
- https://git-scm.com/book/ko/v1/%EB%B6%84%EC%82%B0-%ED%99%98%EA%B2%BD%EC%97%90%EC%84%9C%EC%9D%98-Git-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8%EC%97%90-%EA%B8%B0%EC%97%AC%ED%95%98%EA%B8%B0
- https://tuwlab.com/ece/22202
```