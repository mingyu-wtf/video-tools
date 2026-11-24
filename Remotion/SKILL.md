# Remotion

- **저장소:** https://github.com/remotion-dev/remotion
- **별:** 약 75,404개 (2026-11-25 확인)
- **라이선스:** 소스 공개이나 상업 사용 시 회사 라이선스 필요할 수 있음 (LICENSE 확인)

## 용도
React 코드로 영상을 프로그래밍 방식으로 만드는 영상 프레임워크. "영상을 코드로 소유"하는 방식.

## 핵심 기능
- React 컴포넌트로 장면·애니메이션·자막·효과·전환을 코드로 정의
- 인터랙티브 편집, 에이전트 기반 자동 생성, 대량 배치 렌더링
- 자막, 폰트, 색 보정, 도형, 사운드 효과 지원, Lambda/Vercel 렌더링

## MG의 쇼츠/영상 제작에서 활용
- React 코드로 모션 그래픽(타이틀 애니메이션, 자막 강조, 카운트다운, 차트)을 렌더
- 템플릿 하나로 텍스트만 바꿔 쇼츠를 대량 생산 (예: 카드뉴스 → 영상)
- 데이터(가격·순위 등)가 바뀌는 영상을 자동 생성

## 설치 / 기본 사용법
```bash
npx create-video@latest
# 프로젝트 안에서
npm run dev    # 미리보기
npm run build  # 렌더링
```
- Node.js 필요. 문서 1,200페이지 이상 (remotion.dev/docs)

## 함께 쓰는 도구
three.js(3D 장면), Pillow(썸네일), FFmpeg(최종 인코딩·합성), edge-tts/Chatterbox(내레이션)
