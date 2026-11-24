# Supertonic

- **저장소:** https://github.com/supertone-oss-archive/supertonic
- **별:** 약 13,760개 (2026-11-25 확인)
- **라이선스:** MIT
- **주의: 저장소가 보관(archived) 상태. 2026년 7월 23일 공지 이후 개발·지원 종료. 코드·모델은 아카이브로만 제공.**

## 용도
ONNX Runtime으로 동작하는 번개처럼 빠른 온디바이스 다국어 TTS. 클라우드 없이 기기 안에서만 동작.

## 핵심 기능
- 99M 파라미터 오픈 웨이트 모델, 31개 언어 지원 (한국어 `ko` 포함, 언어 모를 땐 `lang="na"`)
- 44.1kHz 고음질 WAV 출력, 표현 태그 10종 (`<laugh>` `<breath>` `<sigh>` 등)
- Python·Node.js·브라우저(WebGPU)·Java·C++·C#·Go·Swift·Rust·Flutter 등 다중 런타임 SDK
- GPU 불필요, 라즈베리파이·이리더에서도 동작

## MG의 쇼츠/영상 제작에서 활용
- 가볍게 돌아가는 로컬 음성 합성 — 인터넷 없이 빠르게 내레이션 생성
- Chatterbox보다 가볍고 빠름. 초안 내레이션·대량 쇼츠 음성 생성에 적합
- 한국어 포함 31개 언어로 다국어 쇼츠 내레이션

## 설치 / 기본 사용법
```bash
git clone https://github.com/supertone-oss-archive/supertonic.git
cd supertonic
python3.11 -m venv .venv && source .venv/bin/activate
python -m pip install huggingface_hub
hf download supertone-oss-archive/supertonic-3 \
  --revision aafc6e32416a594460b32413efc49d7fe4ce6d46 --local-dir assets
python -m pip install -r py/requirements.txt
cd py
python example_onnx.py --text "이 음성은 로컬에서 생성했습니다." --lang ko
# 결과: py/results/ 에 WAV 저장
```

## 함께 쓰는 도구
edge-tts(무료 시험용), Chatterbox(고품질 복제 음성), FFmpeg(오디오 믹스)
