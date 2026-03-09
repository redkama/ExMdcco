# ExMdcco

React로 제작한 `맛닭꼬` 브랜드 사이트 클론 프로젝트입니다. 메인 랜딩, 메뉴 소개, 매장 찾기, 장바구니, 커뮤니티 화면까지 하나의 SPA로 구현했고, GitHub Pages에 배포할 수 있도록 `basename`과 `homepage` 설정을 맞췄습니다.

배포 주소: <https://redkama.github.io/ExMdcco>

## 프로젝트 개요

- 브랜드 사이트 형태의 React SPA 구현
- `react-router-dom` 기반 페이지 라우팅 구성
- `Redux Toolkit`으로 장바구니 상태 관리
- `Swiper`로 메인 배너와 메뉴/매장 슬라이드 UI 구현
- `Kakao Maps` SDK를 활용한 매장 위치 모달 표시

## 주요 기능

- 메인 페이지
  - 메인 비주얼 배너
  - 추천 메뉴 / 매장 슬라이더
  - 유튜브 섹션
  - 신메뉴 / 뉴스 섹션
- 메뉴 페이지
  - 카테고리 필터
  - 가격순 / 이름순 정렬
  - 메뉴 상세 페이지 이동
- 메뉴 상세
  - 상세 설명 탭 UI
  - 장바구니 담기
  - 토스트 메시지 표시
- 장바구니
  - 수량 증가 / 감소
  - 상품 삭제
  - 총 금액 / 배송비 계산
- 매장 찾기
  - 시/도, 구/군, 키워드 검색
  - 배달 가능 여부 필터
  - 카카오맵 모달로 위치 확인
- 커뮤니티
  - 게시글 목록 / 상세
  - 글 작성 / 수정 / 삭제
  - 제목, 작성자, 내용 검색

## 기술 스택

- React 19
- React Router DOM 6
- Redux Toolkit / React Redux
- React Bootstrap / Bootstrap
- Swiper
- Styled Components
- Kakao Maps JavaScript SDK

## 폴더 구조

```text
src
├─ components   # 공통 UI, 메인 섹션, 장바구니, 게시판, 지도 모달
├─ pages        # 라우트 페이지 단위 컴포넌트
├─ db           # 메뉴 / 매장 / 뉴스 목업 데이터
├─ App.js       # 전체 라우팅 구성
├─ index.js     # BrowserRouter, Redux Provider 연결
└─ store.js     # Redux store 및 cart/user slice
```

## 실행 방법

```bash
npm install
npm start
```

개발 서버 실행 후 브라우저에서 `http://localhost:3000/ExMdcco` 또는 라우팅 설정에 맞는 기본 주소를 확인하면 됩니다.

## 빌드

```bash
npm run build
```

- `package.json`의 `homepage`가 `https://redkama.github.io/ExMdcco`로 설정되어 있습니다.
- `BrowserRouter basename="/ExMdcco"` 설정이 포함되어 있어 GitHub Pages 서브경로 배포를 기준으로 동작합니다.

## 배포 메모

GitHub Pages 배포 시 아래 두 설정이 이미 반영되어 있습니다.

- `package.json`의 `homepage`
- `src/index.js`의 `BrowserRouter basename`

정적 호스팅에서 새로고침 대응을 위해 `public/404.html`도 함께 포함되어 있습니다.

## 빌드 확인

로컬에서 `npm run build` 실행 기준 프로덕션 빌드 통과했습니다.  


## 참고

- 일부 화면 데이터는 `src/db` 내부 목업 데이터로 구성되어 있습니다.
- 지도 기능은 `public/index.html`에 로드된 Kakao Maps SDK를 사용합니다.
