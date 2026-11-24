# edge-tts

- **저장소:** https://github.com/rany2/edge-tts
- **별:** 약 12,634개 (2026-11-25 확인)
- **라이선스:** GPL-3.0 (저장소 내 gpl-3.0.txt)

## 용도
Microsoft Edge의 온라인 TTS 서비스를 Edge 없이 Python에서 쓰는 모듈. 무료.

## 핵심 기능
- 다양한 언어·목소리(Neural 음성) 지원, 속도·볼륨·피치 조절
- 자막(.srt) 동시 생성, 음성 목록 조회, Python 모듈로 사용 가능
- **주의: Microsoft 온라인 서비스에 의존하므로 인터넷 필요. 서비스 정책 변경 시 동작이 바뀔 수 있음**

## MG의 쇼츠/영상 제작에서 활용
- 무료로 시험용 내레이션을 빠르게 뽑는 음성 합성 — 대본 초안의 목소리를 바로 확인
- 한국어 내레이션 초안 생성 → Chatterbox/Supertonic으로 최종 목소리 교체
- 자막 파일(.srt)을 함께 받아 타이밍 확인

## 설치 / 기본 사용법
```bash
pip install edge-tts
# CLI만 쓰려면: pipx install edge-tts
```
```bash
# 기본 사용
edge-tts --text "안녕하세요" --write-media hello.mp3 --write-subtitles hello.srt
# 목소리 목록
edge-tts --list-voices
# 목소리 지정 (한국어 예: ko-KR-SunHiNeural 등 목록에서 확인)
edge-tts --voice ko-KR-SunHiNeural --text "안녕하세요" --write-media hello.mp3
# 속도/볼륨/피치 조절
edge-tts --rate=-10% --volume=+10% --pitch=+5Hz --text "안녕하세요" --write-media hello.mp3
```

## 함께 쓰는 도구
faster-whisper(생성 음성 전사·검증), Chatterbox/Supertonic(최종 내레이션), FFmpeg(오디오 믹스)
