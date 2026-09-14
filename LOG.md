# 📋 주한태 작업 내역 로그 (Work Log)

본 문서는 `docs/AI_REPORT_LOG.md` 전체 작업 로그 중 **주한태 팀원**이 직접 개발·기여한 항목과 통합 반영된 작업 내역을 추출하여 정리한 개발 기록입니다.

---

## 📅 2026-05-27: Firebase 연동 및 냉장고 점수 시스템

- **[신규]** `public/js/core/nutrition-api.js`: 식약처 식품영양성분DB 오픈 API 연동 모듈 구현
- **[신규]** `public/js/core/utils.js`: 냉장고 점수 계산 알고리즘 추가 (`기본 80점 + 영양소가점 + 유통기한가점 - 유통기한감점`)
- **[변경]** `public/js/core/store.js`: `addIngredient`에 `nutritionCategories` 필드 추가
- **[변경]** `public/js/ui/fridge.js`: 재료 등록 시 오픈 API로 5대 영양소 자동 조회 및 저장 연동
- **[변경]** `public/page/fridge.html`: 점수 위젯(`data-fridge-score`) DOM 추가
- **[변경]** `public/css/fridge.css`: 콤팩트 미니 점수 위젯 스타일 추가

---

## 📅 2026-05-27: 냉장고 캐릭터 및 레벨업 시스템

- **[신규]** `public/js/core/utils.js`: 냉장고 레벨/EXP 계산, 표정 랜덤 선택, 스프라이트 좌표, 가입일수 계산 함수 추가
- **[신규]** `public/js/core/store.js`: `getUserProfile`, `setFridgeNickname`, `countCookedMeals` 함수 추가
- **[변경]** `public/page/fridge.html`: 냉장고 캐릭터 히어로 영역, 닉네임, 레벨/EXP 바, 액션 버튼 UI 추가
- **[변경]** `public/js/ui/fridge.js`: 닉네임 관리, 레벨/EXP 렌더링, 16개 표정 스프라이트(점수 기준), 기본 닉네임 알림, 스크롤 이동 구현
- **[변경]** `public/css/fridge.css`: 냉장고 히어로, 캐릭터, 레벨 바, 콤팩트 점수, 액션 버튼 스타일 추가

---

## 📅 2026-05-27: 냉장고 UI/UX 전면 개선

- **[변경]** `public/page/fridge.html`: 기존 인라인 재료 등록 폼 제거, 모달 팝업 및 드롭다운 DOM 구조 추가
- **[변경]** `public/js/ui/fridge.js`: 재료 추가 버튼 클릭 시 모달 오픈, 냉장고 열기 버튼 클릭 시 드롭다운 토글 및 모달/드롭다운 닫기 로직 추가
- **[변경]** `public/js/ui/fridge.js`: 검색/보관 필터 변경 시 드롭다운 동시 갱신
- **[변경]** `public/js/ui/fridge.js`: Form submit 후 모달 자동 닫힘 처리
- **[변경]** `public/css/fridge.css`: 냉장고 캐릭터 크기 확대 (200x168 → 300x252)
- **[변경]** `public/js/core/utils.js`: 스프라이트 셀 크기 확대 (200x168 → 300x252)
- **[변경]** `public/js/ui/fridge.js`: 캐릭터 배경 크기 800x672 → 1200x1008px로 확대
- **[신규]** `public/css/fridge.css`: 모달 오버레이/컨텐츠, 드롭다운 헤더/바디/아이템 스타일 추가

---

## 📅 2026-05-28: 대시보드 및 냉장고 UI 개선

- **[변경]** `public/page/dashboard.html`: 대시보드 전면 재디자인 (둥근 배너 + 캐릭터, 2단 그리드 레이아웃, 예산 막대 그래프)
- **[변경]** `public/css/dashboard.css`: 완전 재작성 (둥근 카드 20px, 그림자, 그리드 기반 2단 레이아웃, 예산 바 차트)
- **[변경]** `public/js/ui/dashboard.js`: 예산 사용률/남은 금액/막대 그래프 DOM 렌더링 추가
- **[변경]** `public/page/fridge.html`: 재료 추가 모달 둥근 디자인, 수량+단위 한 줄 배치
- **[변경]** `public/css/fridge.css`: 재료 추가 모달 스타일 추가 (`.modal__content--add`, `.add-modal__form`)
- **[변경]** `public/page/fridge.html`: 닉네임 변경 커스텀 모달 추가
- **[변경]** `public/js/ui/fridge.js`: 브라우저 기본 `window.prompt()` 제거, 커스텀 모달 로직 구현
- **[변경]** `public/css/fridge.css`: 닉네임 모달 스타일 (`.nickname-modal__body`) 및 버튼 추가
- **[변경]** `public/css/fridge.css`: 연필 아이콘 버튼 크기 축소 (22px → 18px)
- **[변경]** `public/js/ui/fridge.js`: 삭제/전체삭제 확인창을 `window.confirm` → 커스텀 확인 모달로 교체
- **[변경]** `public/page/fridge.html`: 커스텀 확인 모달 HTML 추가
- **[변경]** `public/css/fridge.css`: 확인 모달 스타일 (`.modal--confirm z-index:200`) 추가

---

## 📅 2026-05-29: 요리 완료 모달 및 UX 개선

- **[변경]** `public/js/core/utils.js`: `showAlertModal()` 구현 (`window.alert`를 커스텀 모달로 대체)
- **[변경]** `public/js/ui/shopping.js`, `public/js/ui/recipes.js`: `alert` 호출을 `showAlertModal`로 교체
- **[변경]** `public/css/shopping.css`: `.shopping-page` max-width 오버라이드 제거, global `.main` 1160px 기준으로 다른 페이지와 위치 통일
- **[변경]** `public/js/ui/recipes.js`: `startCooking()` 함수 리팩토링 (페이지 내 드롭다운 렌더링 제거, 장보기 목록 추가 후 `/page/shopping.html?recipeUrl=URL`로 리다이렉트)
- **[변경]** `public/js/ui/shopping.js`: URL `recipeUrl` 파라미터 처리 (해당 레시피 자동 아코디언 펼침 + 조리 시작)
- **[변경]** `public/page/shopping.html`: 요리 완료 모달 구조 확장 (이미지 업로드 영역, 자동 계산 비용 요약, AI 확인 영역 추가)
- **[변경]** `public/js/ui/shopping.js`: `openFinishModal()` 냉장고 재료 기반 자동 비용 계산 (`calculateIngredientCost`, `parseRecipeAmount`) 추가
- **[변경]** `public/js/ui/shopping.js`: 이미지 업로드/미리보기/제거 이벤트 핸들러 추가
- **[변경]** `public/js/ui/shopping.js`: AI 판단 버튼 핸들러 연동 (`/api/askGemini` 호출, 확인 완료 시 기록 저장 버튼 활성화)
- **[변경]** `public/css/shopping.css`: finish modal 전용 스타일 추가 (이미지 업로드, 비용 요약, AI 로딩 애니메이션)

---

## 📅 2026-05-29: 요리 완료 모달 세부 UX & 재료 수정

- **[변경]** `public/page/shopping.html`: finish modal 헤더 X 버튼 제거, AI 확인 영역을 이미지 업로드 아래로 이동
- **[변경]** `public/page/shopping.html`: 사용한 재료 영역에 수정 버튼 + 드롭다운 입력 폼 추가
- **[변경]** `public/js/ui/shopping.js`: `renderIngredientRows()` 추가 (체크박스 + 수정버튼 + 드롭다운 HTML 생성)
- **[변경]** `public/js/ui/shopping.js`: `calculateIngredientCost()`에 `overrides` 파라미터 추가 (사용자 수정값 실시간 반영)
- **[변경]** `public/js/ui/shopping.js`: `recalculateCostFromUI()` 추가 (체크박스 상태 변경 시 선택된 재료만 비용 재계산)
- **[변경]** `public/js/ui/shopping.js`: 이벤트 위임(Delegation) 처리 (체크박스 change, 수정버튼 토글, 드롭다운 입력값 change 핸들링)
- **[변경]** `public/css/shopping.css`: `.finish-ingredient-row`, `.finish-ingredient-main`, `.finish-ingredient-edit`, `.finish-ingredient-dropdown` 스타일 추가
- **[변경]** `public/js/ui/shopping.js`: `replaceAmountNumber()` 추가 (원본 단위 보존하며 수량 숫자만 교체, 예: "6개" → "3개")
- **[변경]** `public/js/ui/shopping.js`: `renderIngredientRows()` 저장 버튼 및 `data-ingredient-label`, `data-original-qty` 속성 추가
- **[변경]** `public/js/ui/shopping.js`: 재료 저장 클릭 시 overrides 적용, 체크박스 `data-recipe-qty` 업데이트 및 드롭다운 닫힘 처리
- **[변경]** `public/css/shopping.css`: `.finish-ingredient-dropdown-actions`, `.finish-ingredient-save` 스타일 추가
- **[변경]** `public/css/shopping.css`: `.modal__content` 커스텀 스크롤바 스타일 적용 (6px 슬림 썸, 둥근 모서리)

---

## 📅 2026-05-29: 다중 이미지 업로드 및 저장 피드백 보강

- **[변경]** `public/page/shopping.html`: `finish-image-area`를 다중 이미지 그리드로 전환 (`finish-image-grid`, `finish-image-add`, `finish-image-thumb`, 개별 제거 버튼)
- **[변경]** `public/js/ui/shopping.js`: `activeFinishImages` 배열 상태 관리 (`[{ id, base64 }]` 구조)
- **[신규]** `public/js/ui/shopping.js`: `renderImageGrid()` 추가 (썸네일 + 추가 버튼 동적 렌더링, `FileReader` 다중 비동기 처리)
- **[신규]** `public/js/ui/shopping.js`: `handleImageFiles()` 추가 (`multiple file input` 대응)
- **[변경]** `public/js/ui/shopping.js`: 이미지 제거 클릭 시 해당 인덱스 splice 후 재렌더링
- **[변경]** `public/js/ui/shopping.js`: AI 판정 시 첫 번째 대표 이미지(`activeFinishImages[0]`)만 전송하여 토큰 절약
- **[변경]** `public/js/ui/shopping.js`: 저장 페이로드 구조를 `cookImage(단일)` → `cookImages(배열)`로 확장
- **[변경]** `public/css/shopping.css`: 3열 이미지 그리드, 정사각형 dashed 추가 버튼, 개별 썸네일 제거 버튼 스타일 추가
- **[변경]** `public/page/shopping.html`: 기록 저장 버튼 아래 `.finish-submit-hint` 추가
- **[변경]** `public/js/ui/shopping.js`: `openFinishModal` 시 AI 확인 필요 안내 문구 표시 및 AI 확인 완료 시 힌트 숨김 + 저장 버튼 활성화
- **[변경]** `public/css/shopping.css`: `.finish-submit-hint` 스타일 추가

---

## 📅 2026-05-29: 모바일 AI 조리 도우미 인터랙션 개선 (FAB / 스와이프)

- **[변경]** `public/page/shopping.html`: 우측 하단 AI 플로팅 버튼(`.ai-fab`) 추가 후 우측 중앙 고정 드래그 핸들(`.ai-drag-handle`)로 고도화
- **[변경]** `public/css/shopping.css`: 모바일 AI 패널 하단 50vh 고정 방식에서 우측 슬라이드 인/아웃(`transform: translateX`) 구조로 변경
- **[변경]** `public/css/shopping.css`: 드래그 핸들 스타일링 (우측 중앙, 14x72px, primary 배경, 3개 바 표시, `touch-action: pan-y` 적용으로 세로 스크롤 충돌 방지)
- **[신규]** `public/js/ui/shopping.js`: `initSwipeHandle()` 터치 이벤트(`touchstart`, `touchmove`, `touchend`) 구현
- **[신규]** `public/js/ui/shopping.js`: 스와이프 실시간 translateX 계산 (드래그 중 패널이 손가락을 추적)
- **[신규]** `public/js/ui/shopping.js`: 임계값 기반 snap 열림 (60px 이상 이동 또는 속도 `velocity > 0.4` 시 패널 오픈)
- **[신규]** `public/js/ui/shopping.js`: 가로/세로 방향 필터링 (`Math.abs(deltaX) > Math.abs(deltaY)`)으로 브라우저 스크롤과의 간섭 원천 차단

---

## 📅 2026-05-29: 냉장고 AI 영수증 인식 재료 일괄 추가

- **[신규]** `public/page/fridge.html`: 재료 추가 모달 내 탭 UI 추가 (`직접 입력` / `영수증 인식`)
- **[신규]** `public/page/fridge.html`: 영수증 인식 탭 레이아웃 (업로드 드래그 영역, 로딩 스피너, 추출 결과 테이블, 전체 선택, 일괄 추가 버튼)
- **[신규]** `public/css/fridge.css`: 탭 전환 스타일, 점선 업로드 영역, 로딩 애니메이션, 컴팩트 결과 테이블 및 인라인 input/select 스타일
- **[신규]** `public/js/core/receipt-api.js`: `parseReceipt(imageBase64)` API 래퍼 모듈 구현
- **[신규]** `public/js/ui/fridge.js`: 탭 전환 제어 (`switchAddTab`, `resetReceiptTab`)
- **[신규]** `public/js/ui/fridge.js`: 영수증 파일 업로드 → Base64 변환 → API 호출 → 결과 렌더링 파이프라인 구축
- **[신규]** `public/js/ui/fridge.js`: 추출된 재료 항목(`receiptItems`) 상태 관리, 체크박스 전체 선택/해제, 인라인 항목 편집 지원
- **[신규]** `public/js/ui/fridge.js`: 선택된 재료를 `addIngredient`를 통해 냉장고에 일괄 등록하는 배치 저장 기능 구현

---

## 📅 2026-06-12: 커뮤니티 게시판 시스템 (수다방) 전면 구현

- **[신규]** `public/page/board.html`: 혼밥 수다방 메인 페이지
  - 카테고리 탭 (전체, 혼밥등록, 레시피공유, 재료교환, 자유게시판)
  - 정렬 필터 (최신순, 인기순, 조회순)
  - 다중 검색 (제목+내용, 제목, 작성자)
  - 무한 스크롤(더보기) 뷰
- **[신규]** `public/page/board-form.html`: 게시글 작성/수정 페이지
  - 게시판 타입별 동적 필드 (레시피: 재료/난이도/시간, 교환: 거래위치/유통기한)
  - 현재 위치 자동 불러오기 연동
  - 이미지 최대 5장 첨부 및 Drag & Drop 미리보기
  - 5000자 실시간 글자 수 카운터 프로그레스 바
- **[신규]** `public/page/board-detail.html`: 게시글 상세 보기 페이지
  - 댓글 작성 및 삭제, 대댓글 지원
  - 좋아요(Like) 토글 시스템
  - 게시글/댓글 신고 모달 (스팸, 욕설, 음란물, 개인정보, 기타)
- **[신규]** `public/page/admin-board.html`: 게시판 관리자 패널 (게시글 및 신고 내역 관리)
- **[신규]** `public/css/board.css`: 게시판 전용 반응형 스타일, 툴바, 카테고리 배지, 카드 호버 인터랙션
- **[신규]** `public/css/profile.css`: 사용자 프로필 페이지 스타일 (프로필 히어로, 아바타 편집, 인포 그리드)
- **[신규]** `public/js/core/board-api.js`: Firestore 게시판 코어 API 모듈 구현
  - `createBoardPost`, `getBoardPost`, `listBoardPosts` (startAfter 기반 페이지네이션)
  - `updateBoardPost`, `softDeleteBoardPost`
  - `addComment`, `listComments`, `toggleLike`, `hasLiked`
  - `createReport`, `createNotification`, `listNotifications`, `markNotificationRead`
  - `checkAdmin` 권한 판별 등 CRUD 및 Firestore 트랜잭션 전면 설계
- **[신규]** `public/js/ui/board.js`: 게시판 목록 렌더링, 필터링, 정렬, 무한 스크롤 제어
- **[신규]** `public/js/ui/board-form.js`: 게시글 작성 폼 인터랙션, 타입별 폼 렌더링, Firebase Storage 이미지 업로드
- **[신규]** `public/js/ui/board-detail.js`: 상세 페이지 로직, 댓글/좋아요/신고/조회수 카운트
- **[신규]** `public/js/ui/admin-board.js`: 게시판 관리자 로직, 게시글 삭제 및 신고 조치

---

## 📅 2026-06-22: 피드, 1:1 실시간 채팅, 뱃지 엔진 및 후속 기능

- **[신규]** `public/page/feed.html`: 사용자 개인 피드 페이지 (작성글 모아보기, 팔로워/팔로잉)
- **[신규]** `public/page/chat.html`: 1:1 실시간 메시지 채팅 페이지
- **[신규]** `public/page/admin.html`: 통합 관리자 센터 페이지
- **[신규]** `public/css/feed.css`, `chat.css`, `admin.css`: 피드, 채팅 인터페이스, 관리자 대시보드 전용 스타일시트
- **[신규]** `public/js/core/follow-api.js`: 사용자 간 팔로우/언팔로우 및 팔로우 요청/수락 Firestore API 모듈
- **[신규]** `public/js/core/chat-api.js`: 1:1 채팅방 생성, 메시지 송수신, 읽음 처리, 실시간 onSnapshot 구독 모듈
- **[신규]** `public/js/core/badge-engine.js`: 사용자 활동(요리 횟수, 게시글, 냉장고 관리) 기반 활동 뱃지 엔진
- **[신규]** `public/js/core/footer-injector.js`: 전역 공통 푸터 컴포넌트 자동 주입기
- **[신규]** `public/js/ui/feed.js`: 피드 화면 렌더링, 프로필 정보, 작성 게시글 그리드, 팔로우 토글
- **[신규]** `public/js/ui/chat.js`: 채팅 목록 실시간 갱신, 메시지 말풍선 렌더링, 전송/엔터키 처리, 안 읽은 메시지 카운트
- **[신규]** `public/js/ui/admin.js`: 관리자 패널 회원/게시글/신고 통합 처리 로직
- **[변경]** `public/js/ui/layout.js`: 실시간 알림 구독, 알림 삭제/모두 읽음, 팔로우 요청 수락/거절, 채팅 안 읽음 배지 연동
- **[변경]** `public/js/ui/board-detail.js`: 댓글/대댓글 작성자 프로필 이미지 표시, 작성자/관리자 배지, 1:1 대화 연결
- **[변경]** `public/js/ui/profile.js`: 타 유저 프로필 조회 대응 및 프로필 이미지 동기화
- **[변경]** `public/js/ui/dashboard.js`: 내 게시글 기반 요리 갤러리 필터링 연동, 식단 플래너/배지 연동
- **[신규]** `public/favicon.svg`, `public/og-image-v2.png`: 정적 웹 파비콘 및 오픈그래프 미리보기 에셋
