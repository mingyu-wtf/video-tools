# Hahmlet

- **저장소:** https://github.com/hyper-type/hahmlet
- **별:** 약 81개 (2026-11-25 확인)
- **라이선스:** SIL Open Font License 1.1 (상업 사용 가능)

## 용도
한글+라틴을 지원하는 글꼴 가족 "함렡(Hahmlet)". 1940~50년대 한국 영화 '햄릿' 포스터 타이틀 글자에서 영감.

## 핵심 기능
- 9가지 굵기 + 굵기를 축으로 하는 배리어블 폰트 (한글 문자 최초의 Google Fonts 배리어블 폰트)
- 뾰족한 획과 독특한 텍스처, 시선을 끄는 개성 있는 디자인
- 한글·라틴 이중 타이포그래피에 적합

## MG의 쇼츠/영상 제작에서 활용
- 쇼츠 한 줄 자막에 쓰는 한글 폰트 (개성 있고 눈에 띄는 자막)
- 썸네일·타이틀 카드·카드뉴스의 제목 폰트
- Pillow/Remotion/FFmpeg 자막 렌더링 시 폰트 파일로 지정

## 설치 / 기본 사용법
- Google Fonts에서 "Hahmlet" 검색해 다운로드, 또는 저장소 `fonts/` 폴더의 폰트 파일 사용
- Windows: 폰트 파일 우클릭 → 설치 / macOS: Font Book에 추가
- Pillow 사용: `ImageFont.truetype("Hahmlet-Bold.ttf", 72)`
- FFmpeg 자막: `ffmpeg -i in.mp4 -vf "subtitles=sub.srt:force_style='FontName=Hahmlet,FontSize=48'" out.mp4`
- 직접 빌드: `make build` (yq 필요)

## 함께 쓰는 도구
Pillow(자막 카드), FFmpeg(자막 굽기), Remotion(모션 그래픽 자막)
