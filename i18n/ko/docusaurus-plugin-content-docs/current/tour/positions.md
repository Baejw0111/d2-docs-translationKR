import CodeBlock from '@theme/CodeBlock';
import NearConstant from '@site/static/d2/near-constant.d2';
import NearContainer from '@site/static/d2/near-container.d2';
import NearExplanation from '@site/static/d2/near-explanation.d2';
import NearLabelIcon from '@site/static/d2/near-label-icon.d2';

# 위치 설정

일반적으로, 위치 설정은 레이아웃 엔진이 전적으로 제어합니다. 이는 텍스트에서 다이어그램으로 변환할 때 모든 객체의 위치를 수동으로 정의할 필요가 없다는 뜻으로, D2의 장점 중 하나죠.

하지만 가끔 다이어그램의 위치가 영 마음에 안들 때가 있겠죠? 이를 위한 두 가지 방법이 있습니다.

## `near`

`near`를 사용해 원하는 항목을 다이어그램 주변의 원하는 위치에 배치할 수 있습니다.

:::info 사용 가능한 키워드
`top-left`, `top-center`, `top-right`,

`center-left`, `center-right`,

`bottom-left`, `bottom-center`, `bottom-right`
:::

예제를 살펴볼까요?

### 다이어그램에 제목 추가하기

<CodeBlock className="language-d2">
    {NearConstant}
</CodeBlock>

<div className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/img/generated/near-constant.svg2')}}></div>

### 범례 만들기

<CodeBlock className="language-d2">
    {NearContainer}
</CodeBlock>

<div className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/img/generated/near-container.svg2')}}></div>

### 장문의 글 추가하기

<CodeBlock className="language-d2">
    {NearExplanation}
</CodeBlock>

<div className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/img/generated/near-explanation.svg2')}}></div>

## 레이블과 아이콘 위치 설정

`near`를 `label`과 `icon`에 중첩하여 그들의 위치를 지정할 수 있습니다.

<CodeBlock className="language-d2">
    {NearLabelIcon}
</CodeBlock>

<div className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/img/generated/near-label-icon.svg2')}}></div>

:::info 추가적으로 사용 가능한 키워드

레이블과 아이콘을 배치할 때, 도형의 경계 밖에 위치를 지정하기 위해 `outside-` 접두사를 추가할 수 있습니다.

`outside-top-left`, `outside-top-center`, `outside-top-right`,

`outside-left-center`, `outside-right-center`,

`outside-bottom-left`, `outside-bottom-center`, `outside-bottom-right`

여기서 `outside-left-center`와 `center-left` 간의 단어 순서가 다르다는 점을 유의해주세요.
:::

## 객체를 통한 위치 설정

:::info
이 기능은 현재 TALA에서만 작동합니다. 다른 레이아웃 엔진에서도 가능하게 하기 위해 심(shim)들을 개발 중입니다.
:::

`near`에 다른 객체의 절대 ID를 설정하여 레이아웃 엔진에게 두 객체가 서로 근접해 있어야 한다는 것을 알려줄 수 있습니다.

```d2
vars: {
  d2-config: {
    layout-engine: tala
  }
}
aws: {
  load_balancer -> api
  api -> db
}
gcloud: {
  auth -> db
}

gcloud -> aws

explanation: |md
  # Why do we use AWS?
  - It has more uptime than GCloud
  - We have free credits
| {
  near: aws
}
```

텍스트가 `gcloud` 노드가 아닌 `aws` 노드 근처에 위치하는 것을 확인하세요.

<img src={require('@site/static/img/screenshots/text-2.png').default} alt="text near example" width="800"/>

## TALA엔진에서의 `top`과 `left`

TALA 엔진에서는 객체의 `top`과 `left` 값을 직접 설정할 수 있습니다. 레이아웃 엔진은 다른 객체를 근처에 위치시킵니다.

자세한 내용은 [TALA 사용자 매뉴얼](https://github.com/terrastruct/TALA/blob/master/TALA_User_Manual.pdf) 17쪽을 참조하세요.
