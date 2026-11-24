# Playwright

- **저장소:** https://github.com/microsoft/playwright
- **별:** 약 100,974개 (2026-11-25 확인)
- **라이선스:** Apache-2.0

## 용도
Chromium·Firefox·WebKit을 하나의 API로 조종하는 웹 테스트·자동화 프레임워크.

## 핵심 기능
- 헤드리스/헤디드 브라우저 제어, 자동 대기, 로케이터, 트레이싱·스크린샷·동영상 기록
- Playwright Test(테스트 러너), Playwright CLI(코딩 에이전트용), Playwright MCP(AI 에이전트용), 라이브러리
- Python·.NET·Java 버전도 있음

## MG의 쇼츠/영상 제작에서 활용
- 화면 없이 브라우저를 돌려 three.js 프리비즈 정지컷과 웹 캡처를 자동 수집
- 웹 기반 툴(자막 생성기, 썸네일 도구 등)의 화면을 자동 캡처
- 참고 영상·웹페이지 스크린샷을 일괄 수집해 레퍼런스 보드 제작

## 설치 / 기본 사용법
```bash
npm init playwright@latest
# 또는 라이브러리만
npm i playwright
npx playwright install
```
```js
import { chromium } from 'playwright';
const browser = await chromium.launch();
const page = await browser.newPage();
await page.goto('https://example.com');
await page.screenshot({ path: 'shot.png' });
await browser.close();
```
- MCP 연결: `npx @playwright/mcp@latest` / Claude Code: `claude mcp add playwright npx @playwright/mcp@latest`

## 함께 쓰는 도구
three.js(프리비즈 캡처), Pillow(캡처 후 가공), FFmpeg(캡처 프레임 영상화)
