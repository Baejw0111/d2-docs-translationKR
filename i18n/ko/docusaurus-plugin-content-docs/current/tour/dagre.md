---
pagination_next: tour/elk
---

# Dagre

Dagre는 D2의 기본 레이아웃 엔진입니다.

## 참조 문서

[https://github.com/dagrejs/dagre](https://github.com/dagrejs/dagre)

## 장점

- 매우 빠릅니다.
- MermaidJS에서도 사용되는 엔진으로써, 검증된 엔진이라 할 수 있습니다.
- 일반적으로 좋은 결과를 제공합니다.
- 알고리즘의 기반이 되는 이론은 Graphviz를 작동시키는 이론과 동일합니다.
- 계층적 레이아웃을 잘 렌더링합니다.

## 단점

- 유지보수가 이루어지지 않고 있습니다. 2018년에 개발이 중단되었습니다.
- 연결선이 가끔 이상하게 배치될 수 있습니다([https://github.com/dagrejs/dagre/issues/256](https://github.com/dagrejs/dagre/issues/256)).
- 레이아웃 알고리즘이 계층 구조를 엄격하게 지킵니다. 이는 기본 다이어그램이 계층적이지 않더라도 마찬가지입니다.
- 컨테이너 내의 자식 객체를 다른 컨테이너(또는 다른 컨테이너의 자식 객체)와 연결하는 것은 Dagre에서 기본적으로 지원되지 않습니다. 이를 작동시키기 위해 D2에서는 심 코드를 추가했지만, 이로 인해 핵심 알고리즘에서 고려해야 할 몇 가지 사항이 누락되었습니다.
- 연결선이 다중으로 배치될 경우 직각이 아닌 곡선으로 그려집니다. 미관상 좋지 않은 꼬불꼬불한 선으로 그려질 수 있습니다.

## 갤러리

<div style={{display: "inline-flex", alignItems: "center", width: "100%"}}>
  <div style={{width: "50%"}}
  className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/layout_gallery/sample1-dagre.svg2')}}></div>
  <div style={{width: "50%"}}
  className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/layout_gallery/sample2-dagre.svg2')}}></div>
</div>

<div style={{display: "inline-flex", alignItems: "center", width: "100%"}}>
  <div style={{width: "50%"}}
  className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/layout_gallery/sample3-dagre.svg2')}}></div>
  <div style={{width: "50%"}}
  className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/layout_gallery/sample4-dagre.svg2')}}></div>
</div>

<div style={{display: "inline-flex", alignItems: "center", width: "100%"}}>
  <div style={{width: "50%"}}
  className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/layout_gallery/sample5-dagre.svg2')}}></div>
  <div style={{width: "50%"}}
  className="embedSVG" dangerouslySetInnerHTML={{__html: require('@site/static/layout_gallery/sample6-dagre.svg2')}}></div>
</div>
