# brand-assets

브랜드 제품 이미지 아카이브. 블로그·상세페이지·SNS 에서 **링크로 가져다 쓰는 용도**다.
이미지를 매번 다시 올리지 않고 여기 한 곳에 두고 URL 만 참조한다.

현재 담긴 브랜드: **루딕스(Rudix)** — 드럼 스틱·연습패드·드럼의자 15개 제품.

---

## 1. 경로 규칙

```
<브랜드>/<카테고리>/<제품코드>/<종류>/<제품코드>-<종류>-<번호>-<가로>x<세로>.<확장자>
```

예시

```
rudix/throne/MRNL/thumbnail/MRNL-thumb-00-1000x1000.jpg
rudix/throne/MRNL/detail/MRNL-detail-21-860x1434.jpg
rudix/stick/5A/thumbnail/5A-thumb-00-750x750.png
```

파일명만 봐도 **어느 제품의, 무슨 종류의, 몇 번째, 어떤 해상도** 인지 알 수 있다.
내려받아 다른 폴더에 섞여도 정체를 잃지 않는다.

### 종류 두 가지

| 폴더 | 내용 | 쓰는 곳 |
|---|---|---|
| `thumbnail/` | 쇼핑몰 갤러리 컷. 배경 정리된 제품 사진 | 목록 썸네일, 본문 제품 컷, SNS |
| `detail/` | 상세페이지 긴 이미지를 여백 기준으로 자른 조각 | 본문 설명 이미지, 구조 클로즈업 |

`thumb-00` 이 그 제품의 대표이미지다.
`detail` 조각에는 헤드라인·사진·설명이 한 세트로 들어 있어 그대로 본문에 넣을 수 있다.

---

## 2. 링크 만들기

jsDelivr CDN 을 쓴다.

```
https://cdn.jsdelivr.net/gh/ajh322/brand-assets@main/<경로>
```

`raw.githubusercontent.com` 도 열리지만 CDN 용도가 아니라 권장하지 않는다.
버전을 고정하려면 `@main` 자리에 커밋 해시나 태그를 넣는다.

---

## 3. 무엇이 어디 있는지 찾는 법

1. **`manifest.json`** — 전체 목록. 제품코드별로 파일명·해상도·캡션이 들어 있다.
   기계가 읽는 용도.
2. **각 제품 폴더의 `README.md`** — 같은 내용을 표로. 사람이 읽는 용도.
   `detail` 조각에는 무엇이 찍혔는지 캡션이 붙어 있다.
3. 아래 제품 표 — 코드와 제품의 대응.

---

## 4. 루딕스 제품 코드

| 카테고리 | 코드 | 제품 | 자사몰 |
|---|---|---|---|
| `stick` | `5A` | 드럼스틱 5A | [idx=13](https://rudix.biz/shop_view/?idx=13) |
| `stick` | `5B` | 드럼스틱 5B | [idx=10](https://rudix.biz/shop_view/?idx=10) |
| `stick` | `7A` | 드럼스틱 7A | [idx=11](https://rudix.biz/shop_view/?idx=11) |
| `stick` | `CASE` | 스틱 홀더 케이스 | [idx=7](https://rudix.biz/shop_view/?idx=7) |
| `pad` | `PAD8` | 8인치 연습용 드럼패드 세트 | [idx=8](https://rudix.biz/shop_view/?idx=8) |
| `pad` | `PAD12` | 12인치 연습용 드럼패드 세트 | [idx=6](https://rudix.biz/shop_view/?idx=6) |
| `pad` | `GUIDE` | 루디먼트 가이드 에디션 | [idx=14](https://rudix.biz/shop_view/?idx=14) |
| `throne` | `PSTV` | Pro 새들 벨벳 | [idx=5](https://rudix.biz/shop_view/?idx=5) |
| `throne` | `PSTL` | Pro 새들 레더 | [idx=12](https://rudix.biz/shop_view/?idx=12) |
| `throne` | `MRNL` | Master 라운드 유압 레더 | [idx=15](https://rudix.biz/shop_view/?idx=15) |
| `throne` | `MRNV` | Master 라운드 유압 벨벳 | [idx=16](https://rudix.biz/shop_view/?idx=16) |
| `throne` | `MRTL` | Master 라운드 스크류 레더 | [idx=17](https://rudix.biz/shop_view/?idx=17) |
| `throne` | `MRTV` | Master 라운드 스크류 벨벳 | [idx=18](https://rudix.biz/shop_view/?idx=18) |
| `throne` | `MSNV` | Master 새들 유압 벨벳 | [idx=19](https://rudix.biz/shop_view/?idx=19) |
| `throne` | `MSNL` | Master 새들 유압 레더 | [idx=20](https://rudix.biz/shop_view/?idx=20) |

### 의자 코드 읽는 법

네 글자가 각각 한 가지를 뜻한다.

| 자리 | 의미 | 값 |
|---|---|---|
| 1 | 등급 | `M` Master · `P` Pro |
| 2 | 시트 형태 | `R` 라운드 · `S` 새들 |
| 3 | 높이 조절 | `N` 니트로 유압 · `T` 스크류(로터리 메모리락) |
| 4 | 표면재 | `V` 벨벳 · `L` 레더 |

`MSNL` = Master · 새들 · 니트로 유압 · 레더

---

## 5. 새 이미지를 추가할 때

1. 규칙에 맞는 경로와 파일명으로 넣는다. 해상도를 파일명에 반드시 포함한다
2. 해당 제품 `README.md` 의 표에 한 줄 추가한다
3. `manifest.json` 에도 반영한다
4. 커밋하고 push 한다. jsDelivr 반영에 몇 분 걸릴 수 있다

파일명을 바꾸거나 지우면 **이미 발행된 글의 이미지가 깨진다.** 기존 파일은 건드리지 않고
추가만 한다.

---

## 6. 주의

- **저장소는 공개다.** 미공개 제품 이미지를 넣지 않는다. 지금 담긴 것은 전부
  자사몰에 공개된 판매 중 제품의 이미지다
- **네이버 블로그는 이 링크를 쓸 수 없다.** 스마트에디터가 외부 이미지 src 를
  허용하지 않는다. 네이버에는 원본 파일을 에디터에 직접 올려야 한다.
  티스토리와 아임웹은 링크로 된다
- `detail` 조각의 캡션은 자동 판독 결과라 참고용이다. 정확한 사양은 자사몰 상세페이지를 본다
