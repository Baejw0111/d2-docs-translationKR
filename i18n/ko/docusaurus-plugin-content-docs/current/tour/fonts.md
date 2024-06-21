# 글꼴

D2는 다음 4가지 종류의 글꼴들을 사용합니다.

- [Source Sans Pro](https://fonts.google.com/specimen/Source+Sans+Pro)는 대부분의
  텍스트와 라벨, 마크다운 등에 사용됩니다.
- [Source Code Pro](https://fonts.google.com/specimen/Source+Code+Pro)는 코드 블록과
  클래스 도형의 텍스트에 사용됩니다.
- [Architect's Daughter](https://fonts.google.com/specimen/Architects+Daughter)와
  [Fuzzy Bubbles](https://fonts.google.com/specimen/Fuzzy+Bubbles)는 스케치 모드의
  텍스트에 사용됩니다.

현재 CLI에서는 다음 플래그들을 통해 Source Sans Pro를 사용자의 TTF 파일로 교체하여 글꼴을 커스텀할 수 있습니다.

- `--font-regular`
- `--font-italic`
- `--font-bold`

이 플래그들이 다음과 같이 교체하려는 `.ttf` 파일을 가리키도록 해야 합니다.

```shell
d2 --font-regular=./helvetica-regular.ttf input.d2
```

일관성을 위해 글꼴을 모든 플래그에 대하여 아예 교체하지 않거나 한꺼번에 교체하는 것이 좋습니다. 글꼴 스타일 중 일부만 교체한다면, 누락된 스타일에는 Source Sans Pro가 적용됩니다. 예를 들어, `--font-regular`와 `--font-bold`의 글꼴만 교체하면, 이탤릭체는 Source Sans Pro Italic으로 유지됩니다.
:::info
Do you want to customize the fonts for code or sketch mode? Please raise an Issue on
GitHub. We'll support this if there's demand.
:::
