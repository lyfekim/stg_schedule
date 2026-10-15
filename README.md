# 🎼 악보 → 가사 추출기 (무료 OCR 버전)

PDF·이미지 악보를 여러 개 올리면 페이지별로 가사를 텍스트로 추출합니다.
**API 키·서버·빌드가 필요 없습니다.** `index.html` 하나로 동작하고, 모든 처리가 브라우저 안에서 이루어집니다.

## 사용법
`index.html`을 열거나 GitHub Pages로 배포 → 언어 선택 → PDF/이미지 업로드 → **가사 추출하기**

GitHub Pages: 저장소 **Settings → Pages → Branch: main / (root)**

## 한계
- 일반 OCR이라 오선·음표·코드가 섞인 악보에서는 오탈자와 누락이 많습니다. 결과는 꼭 원본과 대조하세요.
- 선명한 인쇄 악보, 가사 줄이 오선과 떨어져 있는 악보에서 가장 잘 동작합니다. 손글씨·흐린 스캔은 어렵습니다.
- 처음 실행할 때 언어 데이터(수 MB)를 내려받습니다. 인터넷 연결이 필요합니다.
- PDF당 최대 60쪽 (`MAXP`).

## 기술
[Tesseract.js](https://github.com/naptha/tesseract.js) 5.1.1 (OCR) · [pdf.js](https://mozilla.github.io/pdf.js/) 2.16.105 (PDF 렌더링)

## 저작권
악보와 가사는 저작권 보호 대상일 수 있습니다. 본인이 이용 권한이 있는 자료에만 사용하세요.
