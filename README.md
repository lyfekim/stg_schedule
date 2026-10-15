# 🎼 악보 → 가사 추출기

PDF·이미지 악보를 여러 개 올리면 페이지별로 인쇄된 가사를 텍스트로 추출합니다.
빌드 과정 없이 `index.html` 하나로 동작하며, 브라우저에서 Anthropic API(Claude 비전)를 직접 호출합니다.

## 사용법
1. [Anthropic Console](https://console.anthropic.com/)에서 API 키를 발급받습니다.
2. `index.html`을 브라우저로 열거나 GitHub Pages로 배포합니다.
3. API 키를 입력하고 PDF/이미지를 올린 뒤 **가사 추출하기**를 누릅니다.

## GitHub Pages 배포
저장소 **Settings → Pages → Branch: main / (root)** 로 설정하면 `https://<계정>.github.io/<저장소>/` 에서 열립니다.

## ⚠️ 보안 주의
- **API 키를 코드나 저장소에 절대 넣지 마세요.** 이 앱은 사용자가 직접 입력한 키를 해당 브라우저의 localStorage에만 저장합니다.
- 브라우저에서 키를 직접 쓰는 방식은 개인용·소규모용입니다. 불특정 다수에게 공개하려면 서버리스 함수(Cloudflare Workers, Vercel 등)로 API를 중계하고 키를 서버에 보관하세요.

## 설정
- 모델은 `index.html`의 `MODEL` 상수로 바꿀 수 있습니다 (기본값 `claude-sonnet-5-5`).
- PDF당 최대 60쪽까지 처리합니다 (`MAXP`).
- 페이지마다 API를 한 번 호출하므로 분량만큼 비용이 발생합니다.

## 저작권
악보와 가사는 저작권 보호 대상일 수 있습니다. 본인이 이용할 권한이 있는 자료에만 사용하세요.

## 기술 메모
- PDF 렌더링: [pdf.js](https://mozilla.github.io/pdf.js/) 2.16.105 (cdnjs)
- 원본 이미지는 최대 1800px JPEG로 줄여 전송합니다.
