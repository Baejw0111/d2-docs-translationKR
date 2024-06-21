---
pagination_next: tour/dagre
---

import CodeBlock from '@theme/CodeBlock';
import DirectionRight from '@site/static/d2/direction-right.d2';
import DirectionUp from '@site/static/d2/direction-up.d2';

# 개요

다양한 레이아웃 엔진을 지원하는 D2는 레이아웃 엔진 선택에 따라 다이어그램의 전반적인 형태에 큰 영향을 미칠 수 있습니다. 각 레이아웃 엔진은 특정 키워드에 대한 지원 정도도 다릅니다. 이들의 일관성을 유지하기 위해 최선을 다하고 있지만, 결국 저희가 제대로 제어할 수 있는 것은 자체 제작한 레이아웃 엔진이며, 다른 레이아웃 엔진이 지원하는 범위에 대해서는 한계가 존재한다고 할 수 있습니다.

## 레이아웃 엔진

- [dagre](/tour/dagre) (기본 설정): 계층적 레이아웃을 생성하는 빠른 방향 그래프 레이아웃 엔진입니다. Graphviz의 DOT 알고리즘을 기반으로 합니다.
- [ELK](/tour/elk): 이 엔진 또한 방향 그래프 레이아웃 엔진입니다. dagre보다 완성도 있으며, 최근 새로운 버전이 출시되어 유지 보수 또한 원활히 이루어지고 있다고 할 수 있습니다(부분적으로 학술 연구 팀이 작업 중).
- [TALA](/tour/tala): 소프트웨어 아키텍처 다이어그램을 위해 특별히 설계된 새로운 레이아웃 엔진입니다.

원하는 레이아웃 엔진을 선택하고, 만들고 있는 다이어그램에 가장 적합한 엔진을 사용하세요. 각각의 엔진은 장단점이 있으니, 개별 페이지를 방문하여 자세히 알아보세요.

`d2 layout`을 실행해 사용 가능한 레이아웃을 확인해보세요. 각 레이아웃 엔진은 구성 가능한 플래그도 가지고 있으며, `d2 layout dagre`와 같이 `d2 layout [엔진]` 형태의 명령어를 실행하여 찾을 수 있습니다.

사용할 레이아웃을 지정하려면, `--layout=dagre`와 같이 플래그를 통해 설정하거나 `$D2_LAYOUT=dagre`와 같이 환경 변수로 설정할 수 있습니다.

### 레이아웃별 기능

일부 키워드와 기능은 특정 레이아웃 엔진에서만 사용할 수 있습니다. TALA는 저희가 직접 개발하고 유지 관리하는, 완전히 제어할 수 있는 유일한 엔진입니다. Dagre와 ELK에 대한 심 코드를 제작하고 있지만, 일부 기능은 레이아웃 엔진에 근본적인 것이기 때문에 우리가 원하는 모든 것을 지원하려면 해당 엔진들을 포크를 하여 작업을 해야 할 수도 있습니다(앞으로 그렇게 할 계획도 있습니다).

여기에 해당하는 사례들은 다음과 같습니다. 이 기능들은 다른 문서에서도 따로 설명이 되었습니다.

- `near`를 다른 객체에 설정하기: `near`는 모든 레이아웃 엔진에서 상수로 설정할 수 있지만, TALA에서는 객체에 직접적으로 설정할 수도 있습니다.
- 컨테이너의 `width`와 `height`: TALA에도 곧 추가할 예정이지만, 현재는 ELK에서만 사용 가능합니다. 참고로 이 키워드들은 모든 레이아웃 엔진에서 컨테이너가 아닌 객체에 대해서 작동합니다.
- `top`과 `left`로 위치 고정: TALA에서만 작동합니다.
- 부모에서 자식으로의 연결(예: 컨테이너에서 그 자식으로): Dagre에서 작동하지 않습니다.

## 방향

다이어그램이 향하게 될 명시적인 방향을 `direction`에 다음 키워드들로 설정하세요.

:::info 옵션

- `up`
- `down`
- `right`
- `left`

:::

<CodeBlock className="language-d2">
    {DirectionRight}
</CodeBlock>

<div
className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/img/generated/direction-right.svg2')}}></div>

<CodeBlock className="language-d2">
    {DirectionUp}
</CodeBlock>

<div
className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/img/generated/direction-up.svg2')}}></div>

### 컨테이너별 방향 설정 (TALA 전용)

:::info
방향 설정은 TALA를 제외한 모든 레이아웃 엔진에서 전역 수준에서 설정할 수 있습니다. 하지만 이 기능은 각 엔진의 알고리즘의 한계로 인해 계층적이며, 한 방향으로만 작동합니다. 이를 해결하기 위한 방법을 강구하고 있습니다.
:::

```d2
vars: {
  d2-config: {
    layout-engine: tala
  }
}
direction: down
a -> b -> c

b: {
  direction: right
  1 -> 2 -> 3
}

a: {
  direction: left
  foo -> bar
}
```

<img src={require('@site/static/img/screenshots/tala-direction.png').default} alt="directions in TALA" />
