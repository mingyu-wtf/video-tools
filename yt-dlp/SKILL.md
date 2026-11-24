# yt-dlp

- **저장소:** https://github.com/yt-dlp/yt-dlp
- **별:** 약 210,400개 (2026-11-25 확인)
- **라이선스:** Unlicense

## 용도
수천 개 사이트를 지원하는 기능 풍부한 CLI 오디오/비디오 다운로더. youtube-dl의 포크.

## 핵심 기능
- YouTube 등 수천 개 사이트 지원, 포맷 선택·자막 다운로드·메타데이터·SponsorBlock
- 플레이리스트·채널 전체 다운로드, 출력 파일명 템플릿, 플러그인
- Python 라이브러리로 임베드 가능

## MG의 쇼츠/영상 제작에서 활용
- 쇼츠에 넣을 실사 영상 자료(스톡·레퍼런스)를 내려받는 다운로더
- 참고 영상의 자막·썸네일·메타데이터 수집
- **주의: 저작권 있는 영상은 무단 재사용 금지. 본인 영상, 무료 라이선스 자료, 참고용 분석에만 사용할 것**

## 설치 / 기본 사용법
```bash
pip install -U "yt-dlp[default]"
# Windows: yt-dlp.exe, macOS: yt-dlp_macos 다운로드
yt-dlp -U   # 업데이트
```
```bash
# 최고 화질 다운로드
yt-dlp "https://www.youtube.com/watch?v=VIDEO_ID"
# 오디오만 추출
yt-dlp -x --audio-format mp3 "URL"
# 자막 포함
yt-dlp --write-subs --sub-langs ko,en "URL"
# 포맷 확인
yt-dlp -F "URL"
```
- FFmpeg·ffprobe 설치 권장 (영상/오디오 병합·후처리용)

## 함께 쓰는 도구
FFmpeg(다운로드 후 변환·자르기), faster-whisper(다운로드 영상 자막 전사), OpenCV(프레임 분석)
