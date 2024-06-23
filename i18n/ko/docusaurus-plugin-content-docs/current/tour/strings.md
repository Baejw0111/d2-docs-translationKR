---
pagination_next: tour/comments
---

import CodeBlock from '@theme/CodeBlock';
import Strings2 from '@site/static/d2/strings-2.d2';

# 문자열

## 따옴표 없는 문자열

지금까지의 예제에서 따옴표를 사용하지 않았다는 것을 알아챘을 것입니다. D2를 사용하기 쉽게 만드는 것이 우리의 목표이고, 따옴표의 존재는 이러한 목표에 상당히 방해되기 때문입니다.

따옴표는 여러모로 유저를 귀찮게 합니다. 첫째, 열린 따옴표를 닫아야 합니다. 둘째, 단일 따옴표와 이중 따옴표 중 어느 것을 사용했는지 기억해야 합니다. 마지막으로, 구문을 번잡하게 만듭니다.

그 말은 대부분 따옴표에 대해 걱정하지 않아도 된다는 것을 의미합니다!

문자열 앞 뒤에 공백이 있더라도 제거되어 출력됩니다.

```d2
   Office Bulb   :     Philips
            Switch   ->   Office Bulb
```

<div className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/img/generated/strings-1.svg2')}}></div>

따옴표가 없는 문자열은 언어에서 다른 용도로 사용되는 특정 문자를 포함할 수 없습니다. 당신이 사용하면 안 되는 기호를 사용할 경우, 해당 구문이 강조되며 명확히 알 수 있을 것입니다.

## 따옴표 있는 문자열

앞에서 언급한 따옴표 없이 사용하면 안되는 기호를 사용해야 할 경우, 단일 또는 이중 따옴표를 사용해야 합니다.

<CodeBlock className="language-d2">
    {Strings2}
</CodeBlock>

<div className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/img/generated/strings-2.svg2')}}></div>

:::info
텍스트에 단일 따옴표가 포함되어 있으면 이중 따옴표를 사용하고, 그 반대의 경우도 마찬가지입니다. 텍스트에 두 종류의 따옴표가 모두 포함되어 있는 경우, 다른 언어에서처럼 탈출문자 `\`를 사용하여 이중 따옴표를 이스케이프 처리하면 됩니다.
:::

## 자동 서식

블록 내의 문자열의 들여쓰기가 충분하지 않은 경우, 자동 서식 기능이 이를 수정해줍니다.

```d2
parent: {
example_code: |go
  package fs

  type FS interface {
    Open(name string) (File, error)
  }

  type File interface {
    Stat() (FileInfo, error)
    Read([]byte) (int, error)
    Close() error
  }

  var (
    ErrInvalid    = errInvalid()    // "invalid argument"
    ErrPermission = errPermission() // "permission denied"
    ErrExist      = errExist()      // "file already exists"
    ErrNotExist   = errNotExist()   // "file does not exist"
    ErrClosed     = errClosed()     // "file already closed"
  )
|
}
```

Will become:

```d2
parent: {
  example_code: |go
    package fs

    type FS interface {
      Open(name string) (File, error)
    }

    type File interface {
      Stat() (FileInfo, error)
      Read([]byte) (int, error)
      Close() error
    }

    var (
      ErrInvalid    = errInvalid()    // "invalid argument"
      ErrPermission = errPermission() // "permission denied"
      ErrExist      = errExist()      // "file already exists"
      ErrNotExist   = errNotExist()   // "file does not exist"
      ErrClosed     = errClosed()     // "file already closed"
    )
  |
}
```

자동 서식 지정 시 들여쓰기가 부족한 비어 있지 않은 줄이 있는지 확인합니다.
그런 줄이 있다면 해당하는 모든 줄의 앞에 제대로 된 들여쓰기가 추가됩니다.
이렇게 하면 편집기에서 들여쓰기를 올바르게 맞추기 위해 애쓸 필요가 없습니다.
블록의 첫 번째 열에 코드를 붙여넣으면 자동 서식 지정이 이를 수정합니다.

기본 블록 문자열 들여쓰기를 두 칸으로 들여쓴 후 탭을 사용하여 블록 문자열을 들여쓸 수 있습니다.
기본 블록 문자열 들여쓰기의 모든 탭은 자동으로 두 칸으로 변환됩니다.
