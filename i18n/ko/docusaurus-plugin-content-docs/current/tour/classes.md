import CodeBlock from '@theme/CodeBlock';
import StyleClasses1 from '@site/static/d2/style-classes-1.d2';
import StyleClasses2 from '@site/static/d2/style-classes-2.d2';
import MultipleClasses from '@site/static/d2/multiple-classes.d2';
import OrderedClasses from '@site/static/d2/ordered-classes.d2';

# 클래스

클래스는 속성을 집합화하고 재사용할 수 있게 해줍니다.

<CodeBlock className="language-d2">
    {StyleClasses1}
</CodeBlock>

<div className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/img/generated/style-classes-1.svg2')}}></div>

## 연결 클래스

다음과 같은 방식으로 연결에도 클래스를 적용할 수 있습니다.

선언 할 때 적용하는 방법:

```d2
a -> b: {class: something}
```

선언 이후 적용하는 방법:

```d2
a -> b
# ...
(a -> b)[0].class: something
```

## 클래스 재정의

만약 객체가 클래스에서 정의한 속성을 가지고 있다면, 객체의 속성이 클래스의 속성을 재정의합니다.

<CodeBlock className="language-d2">
    {StyleClasses2}
</CodeBlock>

<div style={{width: 100, margin: "0 auto"}} className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/img/generated/style-classes-2.svg2')}}></div>

## 다중 클래스

다음과 같이 다중 클래스를 적용할 수 있습니다.

<CodeBlock className="language-d2">
    {MultipleClasses}
</CodeBlock>

<div style={{width: 200, margin: "0 auto"}} className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/img/generated/multiple-classes.svg2')}}></div>

### 순서와 다중 클래스

다중 클래스가 주어지면, 왼쪽에서 오른쪽으로 순차적으로 적용됩니다.

<CodeBlock className="language-d2">
    {OrderedClasses}
</CodeBlock>

<div style={{width: 200, margin: "0 auto"}} className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/img/generated/ordered-classes.svg2')}}></div>

## 고급: 클래스를 태그로 사용하기

D2로 만든 다이어그램을 후처리하고 싶다면, 클래스를 사용하여 객체에 임의의 태그를 지정할 수 있습니다.
적용한 `class`는 SVG 요소의 `class` 속성으로 작성됩니다.
예를 들어, D2 SVG가 포함된 웹 페이지에서 `.stuff { ... }`와 같은 사용자 정의 CSS를 적용할 수 있습니다(또는 onclick 핸들러 등을 위해 Javascript를 사용할 수 있습니다).
