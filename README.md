# brand-assets

브랜드 제품 이미지 호스팅용 저장소. 블로그와 상세페이지에서 링크로 가져다 쓴다.

## 경로 규칙

```
<브랜드>/<카테고리>/<제품코드>/<종류>-<번호>.<확장자>
```

예: `rudix/throne/MRNL/detail-12.jpg`

| 종류 | 뜻 |
|---|---|
| `gallery-NN` | 제품 사진. `gallery-00` 이 대표이미지 |
| `detail-NN` | 상세페이지 긴 이미지를 여백 기준으로 자른 조각 |

제품별 `README.md` 에 조각마다 무엇이 찍혔는지 캡션 표가 있다.
`manifest.json` 은 같은 내용을 기계가 읽는 형태로 담았다.

## 링크 만들기

jsDelivr CDN 을 쓴다. `raw.githubusercontent.com` 은 CDN 용도가 아니라 권장되지 않는다.

```
https://cdn.jsdelivr.net/gh/ajh322/brand-assets@main/rudix/throne/MRNL/gallery-00.jpg
```

## 루딕스 제품 코드

| 카테고리 | 코드 | 제품 |
|---|---|---|
| stick | `5A` `5B` `7A` | 드럼스틱 3종 |
| stick | `CASE` | 스틱 홀더 케이스 |
| pad | `PAD8` `PAD12` | 8인치 / 12인치 연습용 드럼패드 세트 |
| pad | `GUIDE` | 루디먼트 가이드 에디션 |
| throne | `PSTV` `PSTL` | Pro 새들 — 벨벳 / 레더 |
| throne | `MRNL` `MRNV` | Master 라운드 유압 — 레더 / 벨벳 |
| throne | `MRTL` `MRTV` | Master 라운드 스크류 — 레더 / 벨벳 |
| throne | `MSNV` `MSNL` | Master 새들 유압 — 벨벳 / 레더 |

의자 코드 읽는 법: `M`aster/`P`ro + `R`ound/`S`addle + `N`itro유압/`T`hread스크류 + `V`elvet/`L`eather

## 주의

네이버 블로그는 외부 이미지 src 를 허용하지 않는다. 네이버에는 이 링크가 아니라
원본 파일을 에디터에 직접 올려야 한다. 티스토리와 아임웹은 링크로 된다.
