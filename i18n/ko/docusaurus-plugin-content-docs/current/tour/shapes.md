import CodeBlock from '@theme/CodeBlock';
import Shapes1 from '@site/static/d2/shapes-1.d2';
import Shapes2 from '@site/static/d2/shapes-2.d2';

# 도형(Shape)

## 기본

다음과 같이 도형을 선언할 수 있습니다.

```d2
imAShape
im_a_shape
im a shape
i'm a shape
# 하이픈 한개로는 연결이 생성되지 않으므로 도형 작명 시 사용 가능
# `a--shape`와 같이 하이픈 2개 사용 시 연결이 생성되므로 주의할 것
a-shape
```

<div className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/img/generated/shapes-1.svg2')}}></div>

세미콜론을 사용하여 같은 줄에 여러 도형을 정의할 수도 있습니다.

```d2
SQLite; Cassandra
```

기본적으로 도형의 레이블은 도형의 키와 동일합니다.
그러나 레이블을 따로 지정하고 싶다면 다음과 같이 새 레이블을 지정하세요.

```d2
pg: PostgreSQL
```

도형의 기본 타입은 `rectangle`(직사각형)입니다.
타입을 바꾸고 싶다면 `shape` 속성을 사용할 수 있습니다.

```d2
Cloud: my cloud
Cloud.shape: cloud
```

## 예시

```d2
pg: PostgreSQL
Cloud: my cloud
Cloud.shape: cloud
SQLite; Cassandra
```

<div className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/img/generated/shapes-2.svg2')}}></div>

:::info
키는 대소문자를 구분하지 않습니다.
따라서 `postgresql`과 `postgreSQL`은 동일한 도형을 가리킵니다.
:::

:::info 도형 카탈로그

<div className="embedSVG overflow" dangerouslySetInnerHTML={{__html: require('@site/static/img/generated/shapes-3.svg2')}}></div>

`shape` 속성이 ​​취할 수 있는 다른 특수한 타입들이 더 있지만, 그건 다음 섹션에서 다루도록 하겠습니다.
:::
