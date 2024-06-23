# TALA

Terrastruct에서 개발한 소프트웨어 아키텍처 다이어그램을 위해 특별히 설계된 고유의 레이아웃 엔진입니다.

Terrastruct의 사유 소프트웨어이며, 클로스드 소스인 TALA는 D2와 구분되어 설치됩니다. 이는 100% 무료인 동시에 오픈 소스인 D2와 확실하게 구분하기 위해서입니다. [여기](https://github.com/terrastruct/tala#installation)에서 다운로드할 수 있습니다:

## 참조 문서

[https://terrastruct.com/tala/](https://terrastruct.com/tala/)

TALA에 대한 최신 정보는 [공식 TALA 매뉴얼](https://github.com/terrastruct/TALA/blob/master/TALA_User_Manual.pdf)을 참조하세요.

## 장점

- 일반적인 직교 레이아웃 엔진으로서, TALA는 계층이나 트리, 방사형과 같은 한 가지 유형에 제한되지 않습니다. 기본적으로 비계층적인 레이아웃에 대해, TALA는 화이트보드에 사람이 그리듯 다이어그램을 생성할 수 있습니다.
- `top`과 `left`를 사용하여 위치를 고정할 수 있습니다.
- 대칭성을 고려하며 선호합니다.
- 컨테이너를 일급 고려사항으로 취급합니다.
- 컨테이너별로 `direction`을 설정할 수 있습니다.
- `near`는 다른 모양으로 지정될 수 있습니다.
- `sql_table`에 대한 연결은 정확한 행을 가리킵니다.
- 동적으로 레이블의 위치를 지정하여 요소가 가려지는 것을 방지합니다.
- 그리드 셀 간의 연결에는 직선만 사용되지 않으며, TALA의 라우팅 엔진으로 처리됩니다.

## 단점

- 유료입니다.
- 상대적으로 세상 밖에 나온 지 얼마 되지 않았습니다. 개발된 지 약 2년밖에 되지 않았으며, 다른 레이아웃 엔진들은 10년 이상의 시간동안 개발되었습니다.
- 다른 레이아웃 엔진보다 더 무작위적입니다. 레이블을 약간만 바꿔도 완전히 다른 레이아웃으로 변할 수 있습니다.

## 갤러리

<div style={{display: "inline-flex", alignItems: "center", width: "100%"}}>
  <div style={{width: "50%"}}
  className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/layout_gallery/sample1-tala.svg2')}}></div>
  <div style={{width: "50%"}}
  className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/layout_gallery/sample2-tala.svg2')}}></div>
</div>

<div style={{display: "inline-flex", alignItems: "center", width: "100%"}}>
  <div style={{width: "50%"}}
  className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/layout_gallery/sample3-tala.svg2')}}></div>
  <div style={{width: "50%"}}
  className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/layout_gallery/sample4-tala.svg2')}}></div>
</div>

<div style={{display: "inline-flex", alignItems: "center", width: "100%"}}>
  <div style={{width: "50%"}}
  className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/layout_gallery/sample5-tala.svg2')}}></div>
  <div style={{width: "50%"}}
  className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/layout_gallery/sample6-tala.svg2')}}></div>
</div>

## 다른 시드 사용하기

TALA의 핵심 알고리즘은 난수를 초기 배치와 반복성을 결정할 때 사용합니다. 레이아웃이 만족스럽지 않는 경우, `--tala-seeds` 플래그로 시드를 직접 지정하여 다른 레이아웃을 생성할 수 있습니다. 예를 들어, 위의 다이어그램과 동일하지만 `--tala-seeds=2`로 설정된 것입니다.

<div style={{display: "inline-flex", alignItems: "center", width: "100%"}}>
  <div style={{width: "50%"}}
  className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/layout_gallery/sample5-tala-2.svg2')}}></div>
  <div style={{width: "50%"}}
  className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/layout_gallery/sample6-tala-2.svg2')}}></div>
</div>
