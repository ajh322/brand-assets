# brand-assets

브랜드 제품 이미지 아카이브. 블로그·상세페이지·SNS 에서 **링크로 가져다 쓰는 용도**다.
이미지를 매번 다시 올리지 않고 여기 한 곳에 두고 URL 만 참조한다.

담긴 브랜드는 둘이다.

| 브랜드 | 제품 | 사진 | 상세 | 자사몰 |
|---|---|---|---|---|
| **루딕스 (Rudix)** | 드럼 스틱·연습패드·드럼의자 15개 | 67 | 372 | `rudix.biz` |
| **SHL (시니어 건강 연구소)** | 지팡이·장갑 7개 | 77 | 169 | `shl.ltd` |

루딕스는 광고 착지용 랜딩이 따로 있다(`start.rudix.biz`, 전 페이지 noindex).
자르기 전 상세 원본도 별도 저장소에 있다.

**글 쓸 때는 `ASSETS_RUDIX.md` / `ASSETS_SHL.md` 를 보면 된다.** 제품별로 전체
URL 이 적혀 있어 그대로 복사해 쓸 수 있다. 클로드 프로젝트에도 같은 파일이
올라가 있다.

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
자르기 전 **원본**은 별도 저장소에 있다 — <https://github.com/ajh322/brand-assets-source>
jsDelivr 가 저장소 하나를 **50MB 까지만** 서빙하기 때문이다. 원본(약 40MB)을 여기
같이 두면 저장소 전체가 403 이 되어 **이미 발행된 글의 이미지까지 한꺼번에 깨진다.**
이 저장소를 50MB 아래로 유지하는 것이 규칙이다.

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

| 카테고리 | 코드 | 제품 | 사진 | 조각 | 자사몰 | 랜딩 |
|---|---|---|---|---|---|---|
| `stick` | `5A` | 히코리 드럼스틱 5A | 8 | 19 | [상품](https://rudix.biz/shop_view/?idx=13) | [랜딩](https://start.rudix.biz/sticks/5a/) |
| `stick` | `5B` | 히코리 드럼스틱 5B | 8 | 18 | [상품](https://rudix.biz/shop_view/?idx=10) | [랜딩](https://start.rudix.biz/sticks/5b/) |
| `stick` | `7A` | 히코리 드럼스틱 7A | 8 | 18 | [상품](https://rudix.biz/shop_view/?idx=11) | [랜딩](https://start.rudix.biz/sticks/7a/) |
| `stick` | `CASE` | 드럼스틱 홀더 케이스 가방 | 5 | 19 | [상품](https://rudix.biz/shop_view/?idx=7) | [랜딩](https://start.rudix.biz/accessories/stick-holder/) |
| `pad` | `PAD8` | Master 8인치 연습용 드럼패드 세트 | 9 | 37 | [상품](https://rudix.biz/shop_view/?idx=8) | [랜딩](https://start.rudix.biz/pads/8-master/) |
| `pad` | `PAD12` | Pro 12인치 연습용 드럼패드 세트 | 7 | 22 | [상품](https://rudix.biz/shop_view/?idx=6) | [랜딩](https://start.rudix.biz/pads/12-pro/) |
| `pad` | `GUIDE` | 루디먼트 가이드 에디션 | 9 | 14 | [상품](https://rudix.biz/shop_view/?idx=14) | [랜딩](https://start.rudix.biz/pads/guide-edition/) |
| `throne` | `PSTV` | Pro 안장형 스크류 드럼의자 PSTV | 3 | 20 | [상품](https://rudix.biz/shop_view/?idx=5) | [랜딩](https://start.rudix.biz/thrones/pstv/) |
| `throne` | `PSTL` | Pro 안장형 스크류 드럼의자 PSTL | 4 | 19 | [상품](https://rudix.biz/shop_view/?idx=12) | [랜딩](https://start.rudix.biz/thrones/pstl/) |
| `throne` | `MRNL` | Master 원형 유압 드럼의자 MRNL | 1 | 32 | [상품](https://rudix.biz/shop_view/?idx=15) | [랜딩](https://start.rudix.biz/thrones/mrnl/) |
| `throne` | `MRNV` | Master 원형 유압 드럼의자 MRNV | 1 | 32 | [상품](https://rudix.biz/shop_view/?idx=16) | [랜딩](https://start.rudix.biz/thrones/mrnv/) |
| `throne` | `MRTL` | Master 원형 스크류 드럼의자 MRTL | 1 | 29 | [상품](https://rudix.biz/shop_view/?idx=17) | [랜딩](https://start.rudix.biz/thrones/mrtl/) |
| `throne` | `MRTV` | Master 원형 스크류 드럼의자 MRTV | 1 | 31 | [상품](https://rudix.biz/shop_view/?idx=18) | [랜딩](https://start.rudix.biz/thrones/mrtv/) |
| `throne` | `MSNV` | Master 안장형 유압 드럼의자 MSNV | 1 | 31 | [상품](https://rudix.biz/shop_view/?idx=19) | [랜딩](https://start.rudix.biz/thrones/msnv/) |
| `throne` | `MSNL` | Master 안장형 유압 드럼의자 MSNL | 1 | 31 | [상품](https://rudix.biz/shop_view/?idx=20) | [랜딩](https://start.rudix.biz/thrones/msnl/) |
| `cane` | `BUDDYCANE` | 버디케인 카본 4발 지팡이 | 13 | 30 | [상품](https://shl.ltd/shop_view/?idx=3) | [랜딩]() |
| `glove` | `GLOVE` | 치매장갑 | 7 | 40 | [상품](https://shl.ltd/shop_view/?idx=4) | [랜딩]() |
| `cane` | `FOLD` | 접이식 4단 폴딩 지팡이 | 12 | 22 | [상품](https://shl.ltd/shop_view/?idx=5) | [랜딩]() |
| `cane` | `OFFSET` | 오프셋 지팡이 | 11 | 22 | [상품](https://shl.ltd/shop_view/?idx=6) | [랜딩]() |
| `cane` | `OFFSET4` | 오프셋 4발 지팡이 | 11 | 19 | [상품](https://shl.ltd/shop_view/?idx=7) | [랜딩]() |
| `cane` | `LED4` | LED 4발 지팡이 | 11 | 19 | [상품](https://shl.ltd/shop_view/?idx=8) | [랜딩]() |
| `cane` | `LEDSEAT` | LED 의자 지팡이 | 12 | 17 | [상품](https://shl.ltd/shop_view/?idx=9) | [랜딩]() |
| `busybook` | `COMMON` | 비지북 테마 공용 상세 (오션/정글) | 0 | 104 | [상품]() | [랜딩]() |
| `busybook` | `OCEAN` | 비지북 오션 | 9 | 0 | [상품]() | [랜딩]() |
| `busybook` | `JUNGLE` | 비지북 정글 | 9 | 0 | [상품]() | [랜딩]() |
| `busybook` | `FARM` | 비지북 농장 | 7 | 13 | [상품]() | [랜딩]() |
| `busybook` | `DINO` | 비지북 공룡 | 7 | 15 | [상품]() | [랜딩]() |

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

## 4-1. SHL 제품 코드

| 카테고리 | 코드 | 제품 | 사진 | 상세 | 공장코드 | 자사몰 |
|---|---|---|---|---|---|---|
| `cane` | `BUDDYCANE` | 버디케인 카본 4발 지팡이 | 13 | 30 | — | [상품](https://shl.ltd/shop_view/?idx=3) |
| `glove` | `GLOVE` | 치매장갑 | 7 | 40 | — | [상품](https://shl.ltd/shop_view/?idx=4) |
| `cane` | `FOLD` | 접이식 4단 폴딩 지팡이 | 12 | 22 | `GB803` | [상품](https://shl.ltd/shop_view/?idx=5) |
| `cane` | `OFFSET` | 오프셋 지팡이 | 11 | 22 | `GB-841` | [상품](https://shl.ltd/shop_view/?idx=6) |
| `cane` | `OFFSET4` | 오프셋 4발 지팡이 | 11 | 19 | `GB-842` | [상품](https://shl.ltd/shop_view/?idx=7) |
| `cane` | `LED4` | LED 4발 지팡이 | 11 | 19 | `GB-830` | [상품](https://shl.ltd/shop_view/?idx=8) |
| `cane` | `LEDSEAT` | LED 의자 지팡이 | 12 | 17 | `GB-830B` | [상품](https://shl.ltd/shop_view/?idx=9) |

⚠️ **폴더명에 공장코드(GB-XXX)를 쓰지 않았다.** 공장이나 사양이 바뀌면
코드가 갈리는데, 저장소 경로는 이미 발행된 글에 박혀 있어 못 바꾼다.
공장코드는 참고용으로 이 표와 각 제품 README 에만 적는다.

## 5. 새 이미지를 추가할 때

0. **저장소 전체 크기가 50MB 를 넘지 않는지 먼저 확인한다.** 넘으면 jsDelivr 가
   전부 403 을 돌려준다. 큰 원본은 `brand-assets-source` 로 보낸다
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
