import CodeBlock from '@theme/CodeBlock';
import Dimensions from '@site/static/d2/dimensions.d2';

# 크기 설정

대부분의 도형에서 `width`(너비)와 `height`(높이)를 지정할 수 있습니다.

:::info
컨테이너에는 이 키워드를 설정할 수 없습니다. 컨테이너는 내부 요소에 맞게 크기가 조정되기 때문입니다.
:::

<CodeBlock className="language-d2">
    {Dimensions}
</CodeBlock>

<div className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/img/generated/dimensions.svg2')}}></div>
