import CodeBlock from '@theme/CodeBlock';
import Tooltip from '@site/static/d2/tooltip.d2';
import Links from '@site/static/d2/links.d2';

# 상호작용

## 툴팁

툴팁은 마우스를 올렸을 때 나타나는 텍스트입니다. 다음 두 가지 용도로 사용하세요.

1. 보조 설명 추가
   - 객체에 설명을 추가하고 싶을 때 사용하세요. 추가적인 정보가 필요한 사람들이 볼거예요.
2. 정리정돈
   - 더 많은 텍스트로 다이어그램을 지저분하게 만드는 대신, 일부를 툴팁에 넣으세요.

<CodeBlock className="language-d2">
    {Tooltip}
</CodeBlock>

`x`와 `y` 위에 마우스를 올려보세요. 툴팁이 보이실 거예요.

<div
className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/img/generated/tooltip.svg2')}}></div>

PNG와 같은 정적 파일 형식으로 내보낼 경우 다음과 같은 사항이 추가됩니다.

1. 모든 툴팁 아이콘을 번호로 변경합니다.
2. 각 번호에 해당하는 부록을 추가합니다.

<img align="center" width="500" src={require('@site/static/img/screenshots/tooltip.png').default} alt="d2 tooltip" />

:::caution
툴팁은 HTML [title](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/title) 태그로 구현되며,
기본적으로 텍스트 형식을 지원합니다. 마크다운 형식을 툴팁에서 사용할 경우 제대로 렌더링되지 않으니, 주의해주세요.
:::

## 링크

링크는 툴팁과 비슷한 형태로, 클릭 시 외부 링크로 이동하게 됩니다.

<CodeBlock className="language-d2">
    {Links}
</CodeBlock>

각 링크를 한번 클릭해 보세요.

<div
className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/img/generated/links.svg2')}}></div>

:::info
Terrastruct 앱을 사용하는 경우, 다른 보드의 경로를 링크로 사용할 수 있습니다.

```d2
x.link: Overview.My Service.Stuff
```

:::
