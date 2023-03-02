# Billage

목표: `Vue`에서 작동하는 상태관리 라이브러리 만들기 (with Vanilla JS)
test 환경 : `Vue3`
참고할 라이브러리 : `Flux`

일단 시작하기에 앞서 현대 웹에서 가장 중요한 부분은 상태관리라고 생각한다. `React`나 `Vue`같은 프론트엔드 프레임워크를 보게되면 상태값을 기준으로 랜더링하고 있다.
현대 웹의 구조가 복잡해 지기 시작하면서 상태관리의 어려움이 생겼다.(고 한다... ㅎㅎ) 예를들어 Props drilling...
그래서 개발을 할때 무조건 사용하는 상태관리툴을 직접 만들어 보면서 이해하고자 한다.
개인적으로 가장 많이 사용하고 있는 `Vue`를 기준으로 적용할 수 있는 상태관리 툴을 만들려고 한다.

## 스토어 이해하기

### Flux 패턴

![Alt text](/Flux.png)
위 그림은 `Flux`패턴이다. 보게 되면 `Dispatcher`, `Store`, `View`로 3개로 구성 되어 있다.
 `Dispatcher`, `Store`, `View`는 독립적은 노드로 입력과 출력이 완전히 구별되어 있다고 한다.
 여기에서 `action`은 새로운 데이터를 가지고 있는 간단한 객체로서 type 프로퍼티로 구별할 수 있다.

- `Dispatcher`: 모든 데이터는 이 부분을 통해 `Store`로 데이터를 업데이트한다. 예를들어 Action을 통해 생긴 새로운 데이터는 Dispatcher를 통해 Store에 저장된다.
- `Store`: 독립적인 세계를 가지고 있으며, 이 부분에 저장된 데이터가 업데이트 하게 될 경우 **change**이벤트를 통해 View에 넘겨주도록 한다.
- `View`: 사용자에게 보여주는 부분이다.

## 개발해야하는 부분

1. 독립적인 `Store`라고 등록하는 부분
2. `Store`에 상태값을 저장하는 기능(최초)
3. `Store`의 상태값을 가져와 `Vue`로 보내주는 기능
4. 새로운 데이터를 `Store`의 특정 상태값으로 업데이트 해주는 기능

---
### Reference

[Flux Overview](https://haruair.github.io/flux/docs/overview.html)
[참고 블로그 ㅎㅎ](https://junilhwang.github.io/TIL/Javascript/Design/Vanilla-JS-Store/#_4-%E1%84%8F%E1%85%A5%E1%86%B7%E1%84%91%E1%85%A9%E1%84%82%E1%85%A5%E1%86%AB%E1%84%90%E1%85%B3-%E1%84%8B%E1%85%AC%E1%84%87%E1%85%AE%E1%84%8B%E1%85%A6-%E1%84%89%E1%85%A1%E1%86%BC%E1%84%90%E1%85%A2%E1%84%85%E1%85%B3%E1%86%AF-%E1%84%86%E1%85%A1%E1%86%AB%E1%84%83%E1%85%B3%E1%86%AF%E1%84%8B%E1%85%A5%E1%84%8C%E1%85%AE%E1%84%80%E1%85%B5)